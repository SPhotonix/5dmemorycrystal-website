# Meta Pixel Event Mapping - 5D Memory Crystal Quiz

**Last Updated:** January 19, 2026  
**Project:** memory-quiz.5dmemorycrystal.com  
**Pixel ID:** 3386392791526045

---

## Overview

This document maps all Meta (Facebook) Pixel events fired throughout the user journey. These events are used for:
- Ad campaign optimization
- Custom audience creation
- Conversion tracking
- ROAS measurement

---

## Funnel Overview

```
PageView → QuizCompleted → CompleteRegistration → InitiateCheckout → Purchase
```

---

## Event Reference

### 1. Standard Events

| Event | When Fired | Location | Properties |
|-------|------------|----------|------------|
| `PageView` | Every page load | `components/MetaPixel.tsx` | *(automatic)* |
| `CompleteRegistration` | User clicks "Proceed to Payment" | `app/order/page.tsx` | See below |
| `InitiateCheckout` | User clicks "Proceed to Payment" | `app/order/page.tsx` | See below |
| `Purchase` | Payment completed | Stripe webhook (future) | `value`, `currency` |

### 2. Custom Events

| Event | When Fired | Location | Properties |
|-------|------------|----------|------------|
| `QuizCompleted` | User completes quiz & submits email | `app/quiz/page.tsx` | See below |

---

## Detailed Event Properties

### PageView (Automatic)
Fires on every page load via the Meta Pixel base code.

```javascript
fbq('track', 'PageView');
```

---

### QuizCompleted (Custom Event)
Fires when user completes the quiz and submits their email.

**File:** `app/quiz/page.tsx`

```javascript
trackMetaEvent('QuizCompleted', {
  content_name: 'Memory Quiz Completion',
  status: 'completed_quiz',
  em: hashedEmail  // SHA-256 hashed, lowercase, trimmed
})
```

| Property | Type | Description |
|----------|------|-------------|
| `content_name` | string | "Memory Quiz Completion" |
| `status` | string | "completed_quiz" |
| `em` | string | SHA-256 hashed email (for Advanced Matching) |
| `event_id` | string | UUID for deduplication with CAPI |

**Custom Conversion Setup:**
- Event: `QuizCompleted`
- Rule: `status` equals `completed_quiz`

---

### CompleteRegistration (Standard Event)
Fires when user clicks "Proceed to Payment" on the order page.

**File:** `app/order/page.tsx`

```javascript
trackMetaEvent('CompleteRegistration', {
  currency: 'USD',
  value: 0,
  email: normalizedEmail,
  country: selectedCountry,
  city: cityValue,
  zip: postalCodeValue,
  content_name: 'Memory Crystal Quiz Lead',
  content_category: selectedVariant  // "personal", "family", or "business"
})
```

| Property | Type | Description |
|----------|------|-------------|
| `currency` | string | "USD" |
| `value` | number | 0 (lead value, not purchase) |
| `email` | string | User's email (for matching) |
| `country` | string | Two-letter country code |
| `city` | string | City name |
| `zip` | string | Postal/ZIP code |
| `content_name` | string | "Memory Crystal Quiz Lead" |
| `content_category` | string | Crystal variant |
| `event_id` | string | UUID for deduplication |

---

### InitiateCheckout (Standard Event)
Fires immediately after CompleteRegistration when user clicks "Proceed to Payment".

**File:** `app/order/page.tsx`

```javascript
trackMetaEvent('InitiateCheckout', {
  value: 100,
  currency: 'USD',
  contents: [{ id: selectedVariant, quantity: 1 }],
  num_items: 1,
  content_type: 'product'
})
```

| Property | Type | Description |
|----------|------|-------------|
| `value` | number | 100 (deposit amount in dollars) |
| `currency` | string | "USD" |
| `contents` | array | `[{ id: "personal/family/business", quantity: 1 }]` |
| `num_items` | number | 1 |
| `content_type` | string | "product" |
| `event_id` | string | UUID for deduplication |

---

### Purchase (Standard Event)
**Status:** Not yet implemented (planned for Stripe webhook)

Will fire when payment is successfully completed.

```javascript
fbq('track', 'Purchase', {
  value: 100.00,
  currency: 'USD',
  content_type: 'product',
  contents: [{ id: variant, quantity: 1 }]
})
```

---

## Event Deduplication

All events include an `event_id` (UUID) for deduplication with Conversions API (CAPI).

```javascript
const eventId = generateMetaEventId() // crypto.randomUUID()
fbq('track', 'EventName', { ...params, event_id: eventId }, { eventID: eventId })
```

When CAPI is implemented, the same `event_id` should be sent server-side to prevent duplicate counting.

---

## Advanced Matching

Email is hashed with SHA-256 before sending for privacy-compliant matching:

```javascript
const hashEmail = async (email) => {
  const normalized = email.trim().toLowerCase()
  const data = new TextEncoder().encode(normalized)
  const digest = await window.crypto.subtle.digest('SHA-256', data)
  return Array.from(new Uint8Array(digest))
    .map(b => b.toString(16).padStart(2, '0'))
    .join('')
}
```

---

## Custom Conversions in Meta Events Manager

### QuizCompleted Conversion
1. Go to Meta Events Manager → Custom Conversions
2. Click "Create Custom Conversion"
3. Settings:
   - **Name:** Quiz Completed
   - **Data Source:** Your Pixel
   - **Event:** QuizCompleted
   - **Rules:** `status` equals `completed_quiz`
4. Save

### Optimization Targets
- **Landing Page Views:** Optimize for `PageView`
- **Quiz Completions:** Optimize for `QuizCompleted` custom conversion
- **Leads:** Optimize for `CompleteRegistration`
- **Purchases:** Optimize for `InitiateCheckout` or `Purchase`

---

## Testing Events

### Using Meta Pixel Helper (Chrome Extension)
1. Install "Meta Pixel Helper" extension
2. Navigate to your site
3. Click the extension icon to see fired events

### Using Test Events in Events Manager
1. Go to Events Manager → Your Pixel → Test Events
2. Enter your website URL
3. Open the site and perform actions
4. Events appear in real-time in the Test Events tab

### Browser Console
```javascript
// Check if fbq is loaded
console.log(typeof fbq)

// View recent Meta events
console.log(window.__lastMetaEvents)

// Manually test an event
fbq('track', 'TestEvent', { test: true })
```

---

## Files Reference

- `components/MetaPixel.tsx` - Pixel base code initialization
- `lib/metaPixel.ts` - Helper functions with event_id support
- `app/quiz/page.tsx` - QuizCompleted event
- `app/order/page.tsx` - CompleteRegistration & InitiateCheckout events

---

## Campaign Optimization Recommendations

| Campaign Goal | Optimize For | Event |
|---------------|--------------|-------|
| Awareness | Landing Page Views | `PageView` |
| Engagement | Quiz Completions | `QuizCompleted` (custom conversion) |
| Lead Generation | Leads | `CompleteRegistration` |
| Sales | Purchases | `InitiateCheckout` or `Purchase` |

---

## Pixel ID & Domain

- **Pixel ID:** 3386392791526045
- **Domain:** memory-quiz.5dmemorycrystal.com
- **Verified:** Yes (DNS TXT record)
