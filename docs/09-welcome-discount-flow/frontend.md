# 09 Welcome discount flow: frontend

## Entry point (no auto popup)
- **Anonymous visitors only** (no session, no prior-login cookie, including private browsing): a "✦ Get 10% off" pill in the desktop nav and a full-width row at the top of the mobile drawer. Logged-in and returning visitors never see it.
- No timed or on-load full-screen popup, ever. In private browsing it would appear on every visit.

## Takeover (full screen, pink → maroon gradient, logo on top, close ✕)
1. **Preference:** "You've got 10% off waiting" + goal buttons (Hair, skin & nails · Gut health · Energy & hydration · Strength & recovery · I'm not sure yet).
2. **Email:** heading "Almost there!", the field, Continue, and a consent line linking to the Privacy Policy.
   - Invalid email → "That email looks incomplete."
   - Already issued → "This email has already been used for a welcome code — check your inbox for it."
3. **Check your inbox:** shows the address, with "Resend verification email" (shows a "Sent again ✓" state) and "Use a different email".
4. **Verified screen** (separate URL, opened from the email link): "You're in!", the unique code with a Copy button (shows "Copied ✓"), "We've emailed it to you too", and a goal-based shop CTA.
- "No thanks, I'll pay full price" is available on steps 1–2.

## After verification
- The code is **auto-applied** to the session. The cart drawer shows a "Welcome 10% · CODE · applied" row, and there is no code field in the drawer.
- The 10% pill disappears for that visitor.
