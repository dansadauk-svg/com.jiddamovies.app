# Jidda Movies Android App

Native Android WebView application for Jidda Movies.

## App details

- App name: Jidda Movies
- Package: `com.jiddamovies.app` (a separate Play Store and Firebase project)
- Website: `https://jiddamovies.com.ng/`
- Version: `1.0.0` (`versionCode 1`)
- Target SDK: Android 36
- Minimum SDK: Android 7.0 / API 24
- Download notifications: enabled

## Included features

- Native WebView without Chrome branding
- Fullscreen HTML5 video support
- Secure movie downloads using logged-in WebView cookies
- File upload support
- Swipe to refresh and offline cache
- Camera-cutout and system-bar safe layout
- Jidda Movies royal-blue and gold launcher and splash branding
- Movie-title downloads with Android progress and completion notifications
- Persistent login until the user explicitly logs out
- Firebase push notifications in the foreground and background
- Automatic subscription to topic `jidda_movies_all`
- Notification taps open the supplied Jidda Movies link inside the app

## GitHub Actions signing secrets

Add these Jidda Movies signing repository secrets:

- `JIDDA_KEYSTORE_BASE64`
- `JIDDA_KEYSTORE_PASSWORD`
- `JIDDA_KEY_PASSWORD`
- `JIDDA_GOOGLE_SERVICES_JSON_BASE64` (optional fallback; `app/google-services.json` is already included)

The dedicated Jidda Movies release-key alias is fixed to `jidda_movies`; no alias secret is required. The workflow produces APK and Play Store AAB artifacts.

The included Firebase Android configuration is registered to `com.jiddamovies.app`. The Base64 secret is only needed if you intentionally remove `app/google-services.json`. Every installation subscribes to topic
`jidda_movies_all`. Send broadcast notifications to that topic to address all
registered devices at once.

## Important

The project uses `https://jiddamovies.com.ng/`. Upload `assetlinks.json` to `https://jiddamovies.com.ng/.well-known/assetlinks.json` before publishing.
