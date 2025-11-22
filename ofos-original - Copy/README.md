# Social Login Setup (Google only)

This project includes client-side placeholders for Google Sign-In on the `loginPage` and `signupPage`.

Files changed:
- `index.html` — added Google sign-in buttons and client-side handlers for both Login and Signup.

Quick setup

1. Obtain credentials
   - Google: Create an OAuth 2.0 Client ID for "Web application" in the Google Cloud Console and copy the `Client ID`.
     - Add `http://localhost` or your site origin in the Authorized JavaScript origins.

2. Configure `index.html`
   - Replace `YOUR_GOOGLE_CLIENT_ID` with your Google Client ID (string).

3. Production considerations
   - Do not rely solely on client-side token parsing for authentication. Send the Google `credential` JWT to your backend and verify it server-side with Google's token verification before creating a session.
   - Create a secure session after verification and set an HttpOnly cookie.

4. Local testing
   - For quick testing, serve the project folder with a static server, e.g. using Python:

```powershell
python -m http.server 8000
```

Then open `http://localhost:8000` in your browser.

5. Where to look in the code
   - The Google buttons are placed in the login and signup boxes; elements `#googleSignInButton` and `#googleSignUpButton` are where the Google buttons are rendered.
   - Temporary UI feedback is shown in `#socialMessage` (login) and `#signupSocialMessage` (signup) on successful sign-in.

If you want, I can:
- Insert your real Google Client ID into `index.html` for you (paste it here to add).
- Wire a small server endpoint to verify tokens and create sessions.
- Improve UI (icons, separate styles) or add sign-out flows.

