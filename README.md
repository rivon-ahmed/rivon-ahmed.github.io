# Boi Campus — GitHub Pages

This repository powers the public web presence for the **Boi Campus** app.

## Structure

```
.
├── index.html                          ← App landing page
├── post/
│   └── index.html                      ← Book post public preview page
└── .well-known/
    ├── assetlinks.json                 ← Android App Links
    └── apple-app-site-association      ← iOS Universal Links
```

## Post Preview URL

```
https://YOUR_GITHUB_USERNAME.github.io/post?id=POST_ID
```

Example:
```
https://rivon-ahmed.github.io/post?id=abc123-def456
```

## Setup Steps

### 1. Create GitHub Repository
- Create a new repo named exactly: `YOUR_USERNAME.github.io`
- Enable GitHub Pages (Settings → Pages → Source: main branch)

### 2. Android App Links — `assetlinks.json`
Replace `REPLACE_WITH_YOUR_SHA256_FINGERPRINT` with your actual SHA-256 key fingerprint.

Get it with:
```bash
keytool -list -v -keystore your-release-key.jks
```
Or from Google Play Console → App integrity → App signing key certificate.

### 3. iOS Universal Links — `apple-app-site-association`
Replace `TEAMID` with your Apple Developer Team ID.
Find it at: https://developer.apple.com/account → Membership → Team ID

### 4. Flutter App — Handle Incoming Links
Add `app_links` package and handle `/post?id=POST_ID` in your app router.

### 5. Share Link Format in Flutter
```dart
final shareUrl = 'https://rivon-ahmed.github.io/post?id=$postId';
Share.share('📚 Check out this book on Boi Campus!\n$shareUrl');
```

## What the Preview Page Shows

✅ Book title, author, edition  
✅ Photos (gallery with swipe)  
✅ Price & negotiability  
✅ Book condition details  
✅ Location, category, campus  
✅ Delivery method  
✅ Description  
✅ Seller name (first name only)  
✅ "Install App" buttons (Play Store + App Store)

❌ Contact number — never shown  
❌ Seller phone/email — never shown  
❌ Personal information — never shown  
