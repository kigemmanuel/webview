# Android WebView App - Simple Template

Turn your website into an Android app in 5 minutes! No Java knowledge needed.

**Forked from [slymax/webview](https://github.com/slymax/webview)** and updated with easy customization tags and auto-build support.

---

## 🚀 Quick Start

### 1. Fork or Download This Project

Click the **Fork** button on GitHub, or [Download ZIP](https://github.com/yourusername/webview/archive/master.zip)

### 2. Open in Android Studio

- Download [Android Studio](https://developer.android.com/studio)
- Open the project folder
- Wait for Gradle sync to finish

### 3. Customize Your App

Search for these tags in Android Studio (press `Ctrl+Shift+F` or `Cmd+Shift+F` on Mac):

#### 🏷️ Search `<APPNAME>` → Change Your App Name

**File:** `app/src/main/res/values/strings.xml`

```xml
<string name="app_name">WebView App</string>
<!-- <APPNAME> - Change "WebView App" to your app's name -->
```

Change `"WebView App"` to your app name like `"My Cool App"`

---

#### 📦 Search `<PACKAGE_NAME>` → Change Package Name (3 places)

**File 1:** `app/build.gradle`
```groovy
applicationId "com.example.app" // <PACKAGE_NAME>
```

**File 2:** `app/src/main/AndroidManifest.xml`
```xml
package="com.example.app" <!-- <PACKAGE_NAME> -->
```
and
```xml
android:name="com.example.app.MainActivity" <!-- <PACKAGE_NAME> -->
```

**File 3:** `app/src/main/java/com/example/app/MainActivity.java`
```java
package com.example.app; // <PACKAGE_NAME>
```

Change all `com.example.app` to something unique like `com.yourname.myapp`

**Important:** After changing, right-click your package folder → **Refactor → Rename** to update the folder structure.

---

#### 🔢 Search `<VERSION_CODE>` and `<VERSION_NAME>` → Change Version

**File:** `app/build.gradle`

```groovy
versionCode 1 // <VERSION_CODE> - Increment this: 1, 2, 3...
versionName "1.0" // <VERSION_NAME> - Your version: "1.0", "2.0"...
```

Update these when you release new versions.

---

#### 🖼️ Search `<ICON>` → Change App Icon

Replace icon files in these folders:
- `app/src/main/res/mipmap-mdpi/ic_launcher.png` (48x48)
- `app/src/main/res/mipmap-hdpi/ic_launcher.png` (72x72)
- `app/src/main/res/mipmap-xhdpi/ic_launcher.png` (96x96)
- `app/src/main/res/mipmap-xxhdpi/ic_launcher.png` (144x144)
- `app/src/main/res/mipmap-xxxhdpi/ic_launcher.png` (192x192)

**Easy Way:** Use [Android Asset Studio](https://romannurik.github.io/AndroidAssetStudio/icons-launcher.html) - upload your icon, download all sizes.

---

#### 🌐 Search `<WEBSITE_URL>` → Change Your Website

**File 1:** `app/src/main/java/com/example/app/MainActivity.java`

```java
mWebView.loadUrl("https://kigemmanuel.github.io"); // <WEBSITE_URL>
```

Change to your website URL.

**File 2:** `app/src/main/java/com/example/app/MyWebViewClient.java`

```java
String hostname = "kigemmanuel.github.io"; // <WEBSITE_URL>
```

Change to your website domain (just the domain part, no `https://`).

---

### 4. Build Your App

**In Android Studio:**
- Click **Build → Build Bundle(s) / APK(s) → Build APK(s)**
- Find your APK in `app/build/outputs/apk/debug/`

**Or use terminal:**
```bash
./gradlew assembleDebug
```

---

## 🤖 Auto-Build with GitHub Actions

Every time you push code, GitHub automatically builds your app!

### Setup (Already Done!)

The `.github/workflows/android-build.yml` file is already configured.

### How to Use

1. **Push your changes:**
   ```bash
   git add .
   git commit -m "Customized my app"
   git push
   ```

2. **Get your APK & AAB:**
   - Go to your GitHub repo
   - Click **Actions** tab
   - Click the latest run
   - Scroll down to **Artifacts**
   - Download `app-debug-apk` (for testing)
   - Download `app-release-aab` (for Play Store)

---

## 📱 Local HTML Files (Optional)

Want to bundle HTML files inside your app instead of loading a website?

1. **Put your HTML files** in `app/src/main/assets/` folder
2. **In MainActivity.java**, change:
   ```java
   // Comment this line:
   // mWebView.loadUrl("https://yoursite.com");
   
   // Uncomment this line:
   mWebView.loadUrl("file:///android_asset/index.html"); // <LOCAL_HTML>
   ```

---

## 🎯 Summary - What to Search & Change

| Search This | Change What | Where |
|------------|-------------|-------|
| `<APPNAME>` | App name | `strings.xml` |
| `<PACKAGE_NAME>` | Package (3 places) | `build.gradle`, `AndroidManifest.xml`, `MainActivity.java` |
| `<VERSION_CODE>` | Version number | `build.gradle` |
| `<VERSION_NAME>` | Version name | `build.gradle` |
| `<ICON>` | App icons | All `mipmap-*` folders |
| `<WEBSITE_URL>` | Your website URL | `MainActivity.java`, `MyWebViewClient.java` |

---

## ⚠️ Important Notes

- **Package name** must be **unique** (like `com.yourname.appname`)
- **Change package in all 3 files** and refactor the folder structure
- **Icons** must be replaced in **all mipmap folders**
- For **Play Store**, you need to build a **signed AAB** (Google it or use Android Studio's GUI)

---

## 🙏 Credits

Original template by [slymax/webview](https://github.com/slymax/webview)

Modified with easy search tags and CI/CD workflow.

---

## 📞 Need Help?

- Check the code comments (they have all the instructions)
- Search for the tags (`<APPNAME>`, `<PACKAGE_NAME>`, etc.)
- Open an issue on GitHub

---

**That's it! Fork, search, change, build! 🚀**