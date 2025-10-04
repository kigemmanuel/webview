# 📱 Android WebView App - Simple Template

**Turn your website into an Android app in 5 minutes!** No Java knowledge needed. No powerful PC required! 🚀

**Forked from [slymax/webview](https://github.com/slymax/webview)** - Enhanced with easy search tags & auto-build workflow.

---

## 🎯 What Does This Do?

Wraps your website into a native Android app. Perfect for blogs, portfolios, or simple web apps!

---

## 🚀 Quick Start

### Step 1: Fork This Repo

1. Click the **⭐ Star** button (top right)
2. Click **Fork** button
3. Now you have your own copy!

**GitHub Actions is already set up!** Just fork and you're ready to build in the cloud. 🎉

---

## ⚙️ Customize Your App (5 Simple Steps)

Search for these tags in your files. Press `Ctrl+F` (or `Cmd+F` on Mac) to find them quickly.

### 1️⃣ Change App Name

**Search:** `<APPNAME>`  
**File:** `app/src/main/res/values/strings.xml`

```xml
<string name="app_name">WebView App</string> <!-- <APPNAME> -->
```

Change `"WebView App"` to your app name.

---

### 2️⃣ Change Package Name (3 Files)

**Search:** `<PACKAGE_NAME>`

The package is your app's unique ID. Change `com.example.app` to something like `com.yourname.myapp`

**File 1:** `app/build.gradle`
```groovy
applicationId "com.example.app" // <PACKAGE_NAME>
```

**File 2:** `app/src/main/AndroidManifest.xml` (appears 2 times)
```xml
package="com.example.app" <!-- <PACKAGE_NAME> -->
android:name="com.example.app.MainActivity" <!-- <PACKAGE_NAME> -->
```

**File 3:** `app/src/main/java/com/example/app/MainActivity.java`
```java
package com.example.app; // <PACKAGE_NAME>
```

**Important:** After changing the package name:
- In Android Studio: Right-click your package → **Refactor → Rename** → Enter new name → Click Refactor
- This updates the folder structure automatically!
- Without Android Studio: Manually rename folders from `com/example/app` to `com/yourname/yourapp`

---

### 3️⃣ Change Version

**Search:** `<VERSION_CODE>` and `<VERSION_NAME>`  
**File:** `app/build.gradle`

```groovy
versionCode 1 // <VERSION_CODE> - Increase by 1 for each update
versionName "1.0" // <VERSION_NAME> - What users see: "1.0", "2.0"
```

---

### 4️⃣ Change App Icon

**Search:** `<ICON>`

Replace `ic_launcher.png` in these folders:
- `mipmap-mdpi` (48x48px)
- `mipmap-hdpi` (72x72px)
- `mipmap-xhdpi` (96x96px)
- `mipmap-xxhdpi` (144x144px)
- `mipmap-xxxhdpi` (192x192px)

**Easy Way:** Use [Android Asset Studio](https://romannurik.github.io/AndroidAssetStudio/icons-launcher.html) - Upload one icon, get all sizes!

**Free Icon Sites:**
- [Flaticon](https://www.flaticon.com/)
- [Icons8](https://icons8.com/)
- [Freepik](https://www.freepik.com/icons)

---

### 5️⃣ Set Your Website

**Search:** `<WEBSITE_URL>`

**File 1:** `app/src/main/java/com/example/app/MainActivity.java`
```java
mWebView.loadUrl("https://kigemmanuel.github.io"); // <WEBSITE_URL>
```
Change to your website URL.

**File 2:** `app/src/main/java/com/example/app/MyWebViewClient.java`
```java
String hostname = "kigemmanuel.github.io"; // <WEBSITE_URL>
```
Change to your domain (no `https://`).

**Example:** If your site is `https://www.mysite.com`, use `"mysite.com"`

---

## 🛠️ Build Your App

### Option 1: GitHub Actions (NO PC NEEDED! ⭐)

**Already set up!** Just push your changes:

```bash
git add .
git commit -m "My customizations"
git push
```

**Download your APK:**
1. Go to **Actions** tab on GitHub
2. Click the latest build (wait for green ✅)
3. Scroll to **Artifacts**
4. Download **app-debug-apk** (test on phone)
5. Download **app-release-aab** (for Play Store)

**Manual trigger:** Actions tab → Android CI → Run workflow

---

### Option 2: Build Locally (Requires Android Studio)

```bash
./gradlew assembleDebug
```

APK location: `app/build/outputs/apk/debug/app-debug.apk`

---

## 📲 Install & Test

1. Download the APK to your phone
2. Open it
3. Allow install from unknown sources
4. Install & test!

---

## 📱 Local HTML (Optional)

Want to bundle HTML files inside the app?

**Search:** `<LOCAL_HTML>`

1. Put files in `app/src/main/assets/`
2. In `MainActivity.java`:
```java
// Comment this:
// mWebView.loadUrl("https://yoursite.com");

// Uncomment this:
mWebView.loadUrl("file:///android_asset/index.html"); // <LOCAL_HTML>
```

---

## 🎯 Quick Reference

| Tag | What to Change | Files |
|-----|---------------|-------|
| `<APPNAME>` | App name | `strings.xml` |
| `<PACKAGE_NAME>` | Package (3 places) | `build.gradle`, `AndroidManifest.xml`, `MainActivity.java` |
| `<VERSION_CODE>` | Version number | `build.gradle` |
| `<VERSION_NAME>` | Version display | `build.gradle` |
| `<ICON>` | App icons | All `mipmap-*` folders |
| `<WEBSITE_URL>` | Your website | `MainActivity.java`, `MyWebViewClient.java` |

---

## ✅ Checklist

- [ ] Changed app name
- [ ] Changed package name (3 files)
- [ ] Refactored folder structure
- [ ] Updated version
- [ ] Replaced icons
- [ ] Set website URL
- [ ] Built with GitHub Actions
- [ ] Tested APK on phone

---

## ⚠️ Common Issues

**Build failed?** Check your code changes - you might have deleted something important.

**White screen?** Check your URL is correct and you have internet permission in `AndroidManifest.xml`.

**App won't install?** Uninstall the old version first or use a different package name.

**Icons not updating?** Clean and rebuild: `Build → Clean Project → Rebuild Project`

---

## 💬 Need Help?

**Have an issue?** [Open an issue on GitHub](https://github.com/yourusername/webview/issues) with:
- What you tried to do
- Error message
- Screenshots

We'll help you out! 🤝

---

## 🙏 Credits

Original: [slymax/webview](https://github.com/slymax/webview)  
Enhanced by the community with ❤️

---

## ⭐ Show Support

If this helped you:
- ⭐ **Star this repo**
- 👤 **Follow me on GitHub**
- 🍴 **Share with friends**

Your support keeps this project alive! 🚀

---

**Happy Building! 📱**

*Fork → Search tags → Change → Push → Download APK. That's it!*