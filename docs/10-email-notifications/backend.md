# 10 Email notifications: backend

- **Shopify notifications** (Settings → Notifications): 03 account invite, 04 password reset, 05 order confirmation, 06 shipping confirmation, 07 delivered, 08 order canceled, 09 refund, 14 abandoned checkout. Paste the templates in and swap the sample values for Liquid.
- **Subscription app** templates: 10 created, 11 upcoming (2 days before the charge), 12 payment failed (retry every 3 days, pause after 3 failures, never auto-cancel), 13 cancelled.
- **Welcome flow:** 01 verify and 02 code are sent by the custom endpoint (09) through Shopify Email / Klaviyo.
- Marketing emails (02, 14) require consent and an unsubscribe link. Abandoned checkout goes only to consented customers, 1h after abandonment.
- Delivery-status emails (06–07) depend on the courier integration sending tracking and delivery events. If the courier doesn't send a "delivered" event, drop 07.
- UTM on every link: `utm_source=email&utm_medium=transactional|marketing&utm_campaign=<email-id>`.
- Reply-to: a monitored support inbox (hello@womanbloom.com).
