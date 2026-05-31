# Firebase Hosting Deploy Notes

This folder contains static app policy pages for Google OAuth and Play-related app information.

## Files used by OAuth

SnapScanCard:

- `snapscancard-home.html`
- `snapscancard.html`
- `snapscancard-terms.html`

Health Log:

- `health-log-home.html`
- `health-log.html`
- `health-log-terms.html`

## First-time setup

Install Firebase CLI if needed:

```bat
npm install -g firebase-tools
```

Log in:

```bat
firebase login
```

If Firebase CLI reports a config-store permission error in this Codex shell, run these commands first:

```bat
set XDG_CONFIG_HOME=%CD%\.firebase-config
firebase.cmd login
```

Create or select a Firebase project in the Firebase console, then deploy from this folder:

```bat
cd /d D:\Android_workspace\myapp-privacy-policy
firebase.cmd deploy --only hosting --project YOUR_FIREBASE_PROJECT_ID
```

After deployment, Firebase will print Hosting URLs similar to:

```text
https://YOUR_FIREBASE_PROJECT_ID.web.app
https://YOUR_FIREBASE_PROJECT_ID.firebaseapp.com
```

Use the deployed URLs in Google Cloud OAuth:

```text
https://YOUR_FIREBASE_PROJECT_ID.web.app/snapscancard-home.html
https://YOUR_FIREBASE_PROJECT_ID.web.app/snapscancard.html
https://YOUR_FIREBASE_PROJECT_ID.web.app/snapscancard-terms.html
```

and:

```text
https://YOUR_FIREBASE_PROJECT_ID.web.app/health-log-home.html
https://YOUR_FIREBASE_PROJECT_ID.web.app/health-log.html
https://YOUR_FIREBASE_PROJECT_ID.web.app/health-log-terms.html
```

If Google OAuth still asks for domain verification, add the Firebase Hosting domain to OAuth Authorized domains and follow Google's verification prompt.
