# PostHog Event Mapping - 5D Memory Crystal Quiz

**Last Updated:** January 19, 2026  
**Project:** memory-quiz.5dmemorycrystal.com  
**PostHog Project:** phc_9SRUkf8I32MrHcnSbZjS4NynSc8fgbUtCT08ddfviul

---

## Overview

This document maps all PostHog events fired throughout the user journey from landing page to purchase completion.

---

## Funnel Overview

```
landing_page_view → quiz_start → quiz_completed → order_page_view → order_submit_clicked → stripe_checkout_opened → stripe_payment_succeeded
```

---

## Event Reference

### 1. Landing & Quiz Start

| Event | Description | Properties |
|-------|-------------|------------|
| `landing_page_view` | User lands on any page | `path`, `utm_source`, `utm_medium`, `utm_campaign`, `utm_content`, `utm_term`, `ref`, `funnel` |
| `quiz_start` | User starts the quiz (clicks "Let's begin") | `funnel: "memory_crystal"`, `step: "start"`, `variant`, `quiz_version` |

### 2. Quiz Progress

| Event | Description | Properties |
|-------|-------------|------------|
| `quiz_[step_id]_viewed` | User views a specific step | `step_id`, `step_title`, `step_index`, `step_number`, `total_steps`, `step_position`, `quiz_progress_percent`, `variant` |
| `quiz_[step_id]_continued` | User continues from a step | `step_id`, `step_title`, `step_index`, `step_number`, `total_steps`, `variant` |
| `quiz_step_view` | Generic step view (legacy) | `step_index`, `step_id`, `step_title` |
| `quiz_step_continue` | Generic step continue (legacy) | `step_index`, `step_id`, `step_title` |
| `quiz_answer_selected` | User selects/deselects an answer | `step_index`, `question_id`, `question_text`, `option_id`, `option_text`, `selected` |
| `question_answered` | User answers a question | `question_id`, `answer_option` |

### 3. Email & Lead Capture

| Event | Description | Properties |
|-------|-------------|------------|
| `email_entered` | User submits email in quiz | `method: "form"`, `identifier_kind: "email"`, `variant`, `quiz_completion` |
| `lead_captured` | Lead is captured | `contact_method`, `offer_presented` |

**Note:** `email_entered` also calls `posthog.identify(email)` to link the anonymous session to the user.

### 4. Quiz Completion

| Event | Description | Properties |
|-------|-------------|------------|
| `quiz_completed` | User completes the quiz | `total_time_s`, `recommended_product`, `duration_s`, `answers_count`, `variant`, `email_submitted` |
| `quiz_abandon` | User leaves before completing | `last_step_index`, `last_step_id`, `last_step_title`, `duration_s` |

### 5. Order Page

| Event | Description | Properties |
|-------|-------------|------------|
| `order_page_view` | User lands on /order page | `variant`, `email`, `funnel: "memory_crystal"` |
| `order_address_lookup_started` | User starts UK postcode lookup | *(props vary)* |
| `order_address_lookup_failed` | UK postcode lookup failed | *(error details)* |
| `order_shipping_address_set` | Shipping address selected | *(props vary)* |

### 6. Checkout & Payment

| Event | Description | Properties |
|-------|-------------|------------|
| `order_submit_clicked` | User clicks "Proceed to Payment" | `variant`, `amount`, `currency`, `country` |
| `order_submit_succeeded` | Stripe session created successfully | `variant`, `amount`, `currency`, `session_id` |
| `order_submit_failed` | Checkout creation failed | `error`, `variant` |
| `stripe_checkout_opened` | Redirecting to Stripe | `variant`, `amount`, `currency`, `session_id` |
| `stripe_checkout_returned` | User returns from Stripe | `canceled`, `referrer`, `variant` |
| `stripe_payment_succeeded` | Payment completed successfully | `revenue`, `payment_method`, `order_id` |
| `stripe_payment_failed` | Payment failed | `error` |

### 7. Legacy/Optional Events

| Event | Description | Properties |
|-------|-------------|------------|
| `checkout_initiated` | Checkout started (legacy) | `package`, `price` |
| `purchase_completed` | Purchase completed (legacy) | `revenue`, `payment_method`, `order_id` |
| `form_field_changed` | Form field value changed | `field_name`, `field_value_length`, `has_value` |
| `form_field_focused` | Form field focused | `field_name` |
| `consent_changed` | Consent checkbox changed | `consent_name`, `granted` |
| `form_submitted` | Generic form submission | `form_name`, `success`, `has_first_name`, `has_last_name`, `has_email` |

---

## User Identification

Users are identified by email when they submit the quiz email field:

```javascript
posthog.identify(email, { email: email })
```

This links the anonymous `distinct_id` to the email, allowing you to track the full journey from ad click to purchase.

---

## Recommended Funnels

### Primary Conversion Funnel
```
quiz_start → quiz_completed → order_page_view → order_submit_clicked → stripe_payment_succeeded
```

### Quiz Completion Funnel
```
quiz_start → quiz_welcome_viewed → quiz_what_matters_most_viewed → quiz_email_viewed → quiz_completed
```

### Checkout Funnel
```
order_page_view → order_submit_clicked → stripe_checkout_opened → stripe_payment_succeeded
```

---

## Properties Glossary

| Property | Type | Description |
|----------|------|-------------|
| `variant` | string | Crystal type: "personal", "family", or "business" |
| `funnel` | string | Always "memory_crystal" |
| `step_id` | string | Quiz step identifier (e.g., "welcome", "email") |
| `step_index` | number | Zero-based step position |
| `amount` | number | Price in cents (e.g., 10000 = $100) |
| `currency` | string | Currency code (e.g., "usd") |
| `country` | string | Two-letter country code (e.g., "US", "GB") |
| `session_id` | string | Stripe checkout session ID |
| `total_time_s` | number | Quiz completion time in seconds |

---

## Testing Events

Open browser console and run:
```javascript
// Check if PostHog is loaded
console.log(window.posthog?.get_distinct_id())

// View recent events sent
console.log(window.__posthog_events_sent)

// Manually test an event
window.posthog.capture('test_event', { source: 'manual' })
```

---

## Files Reference

- `components/PosthogScript.tsx` - PostHog initialization and helper functions
- `app/quiz/page.tsx` - Quiz tracking implementation
- `app/order/page.tsx` - Order page tracking implementation
