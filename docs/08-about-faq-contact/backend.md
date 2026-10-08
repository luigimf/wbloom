# 08 About, FAQ & contact: backend / Shopify

- About: page template with image/text row blocks (image, heading, richtext, "read more" length setting).
- FAQ: a **metaobject** `faq_item` (category, question, answer richtext) so the same items can feed the FAQ page, the PDP accordion and the subscriptions page.
- Contact: `{% form 'contact' %}` → store email. Add a hidden honeypot field for spam.
- Privacy Policy and T&Cs pages must be updated for the welcome flow before launch (see 09).
