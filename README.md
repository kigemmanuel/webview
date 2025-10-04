# 📱 Android WebView App - Simple Template

**Turn your website into an Android app in 5 minutes!** No Java knowledge needed. No powerful PC required - use GitHub Actions to build your app in the cloud! 🚀

**Forked from [slymax/webview](https://github.com/slymax/webview)** and enhanced with:
- ✅ Easy search tags for quick customization
- ✅ Auto-build with GitHub Actions (no powerful PC needed!)
- ✅ Beginner-friendly instructions

---

## 🎯 What is This?

This template lets you wrap your website into a native Android app. Perfect for:
- Converting your blog/website into an app
- Creating a mobile version of your web app
- Building simple hybrid apps without learning Android development

---

## 🚀 Quick Start

### Step 1: Get the Project

**Option A: Fork on GitHub** (Recommended for GitHub Actions)
1. Click the **Fork** button at the top of this page
2. Now you have your own copy!

**Option B: Download ZIP**
1. Click **Code → Download ZIP**
2. Extract the folder

### Step 2: Open in Android Studio (Optional - Skip if using GitHub Actions)

If you have a good PC and want to build locally:
1. Download [Android Studio](https://developer.android.com/studio)
2. Open the project folder
3. Wait for Gradle sync to finish (this takes a few minutes the first time)

**Don't have a good PC?** No problem! Skip this and use GitHub Actions instead (see section above).

---

## ⚙️ Customize Your App

You need to change a few things to make this app yours. Use the search feature in your code editor to find these special tags:

### 🔍 How to Search

**In Android Studio:** Press `Ctrl+Shift+F` (Windows/Linux) or `Cmd+Shift+F` (Mac)

**In VS Code or any editor:** Use the search function to find the tags

---

### 🏷️ 1. Change Your App Name

Search for: **`<APPNAME>`**

**File:** `app/src/main/res/values/strings.xml`

```xml
<string name="app_name">WebView App</string>
<!-- <APPNAME> - Change "WebView App" to your app's name -->
```

**What to do:** Replace `"WebView App"` with your app name

**Example:**
```xml
<string name="app_name">My Awesome App</string>
```

This is the name that appears under your app icon on the phone.

---

### 📦 2. Change Package Name (IMPORTANT!)

Search for: **`<PACKAGE_NAME>`**

The package name is like your app's unique ID. It must be unique across all Android apps. **You need to change it in 3 files:**

#### File 1: `app/build.gradle`

```groovy
applicationId "com.example.app" // <PACKAGE_NAME> - Change this to your unique package name
```

**What to do:** Change `"com.example.app"` to something unique

**Example:**
```groovy
applicationId "com.john.myawesomeapp"
```

**Package name rules:**
- Use lowercase letters only
- Format: `com.yourname.appname`
- No spaces or special characters
- Must be unique (check if it exists on Play Store)

#### File 2: `app/src/main/AndroidManifest.xml`

```xml
<!-- <PACKAGE_NAME> - Must match the package name in build.gradle -->
<manifest
    package="com.example.app"
    xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:tools="http://schemas.android.com/tools">
```

and also this line inside the same file:

```xml
android:name="com.example.app.MainActivity"
<!-- <PACKAGE_NAME> - Must match the package name in build.gradle -->
```

**What to do:** Change both `com.example.app` to match what you put in build.gradle

#### File 3: `app/src/main/java/com/example/app/MainActivity.java`

```java
package com.example.app; // <PACKAGE_NAME> - Must match the package name in build.gradle and AndroidManifest.xml
```

**What to do:** Change `com.example.app` to match your package name

---

### 🗂️ Important: Rename Your Folder Structure

After changing the package name in all 3 files, you need to **rename the actual folders** too!

**In Android Studio (Easiest Way):**

1. In the left sidebar, find the `java` folder
2. You'll see folders like `com → example → app`
3. **Right-click** on the package name (the part that shows like `com.example.app`)
4. Select **Refactor → Rename**
5. Type your new package name (e.g., `com.john.myawesomeapp`)
6. Click **Refactor**
7. Android Studio will automatically rename all folders and update all references!

**Why do this?** The folder structure must match your package name. If your package is `com.john.myapp`, the folders should be `com/john/myapp/`. Android Studio's refactor tool does this automatically!

**Without Android Studio?** You'll need to:
1. Manually rename the folders from `com/example/app` to `com/yourname/yourapp`
2. Make sure all 3 files have the matching package name

---

### 🔢 3. Set Your App Version

Search for: **`<VERSION_CODE>`** and **`<VERSION_NAME>`**

**File:** `app/build.gradle`

```groovy
versionCode 1 // <VERSION_CODE> - Increment this: 1, 2, 3, 4...
versionName "1.0" // <VERSION_NAME> - Your version: "1.0", "2.0", "2.5"...
```

**What to do:**
- **versionCode**: A number. Start with 1, then 2, 3, 4... Each time you update your app, increase this by 1.
- **versionName**: A string. This is what users see. Like "1.0", "2.0", "2.5.1", etc.

**When to change:** Every time you release a new version of your app.

---

### 🖼️ 4. Change Your App Icon

Search for: **`<ICON>`**

Your app icon appears on the phone's home screen. You need **different sizes** of your icon for different devices.

**Where to replace:**
- `app/src/main/res/mipmap-mdpi/ic_launcher.png` (48x48 pixels)
- `app/src/main/res/mipmap-hdpi/ic_launcher.png` (72x72 pixels)
- `app/src/main/res/mipmap-xhdpi/ic_launcher.png` (96x96 pixels)
- `app/src/main/res/mipmap-xxhdpi/ic_launcher.png` (144x144 pixels)
- `app/src/main/res/mipmap-xxxhdpi/ic_launcher.png` (192x192 pixels)

Also replace the round versions:
- `ic_launcher_round.png` in all the same folders

---

### 🎨 Easy Way to Get Icons (FREE Tools!)

Don't want to manually resize icons? Use these FREE online tools:

**Best Option:**
- **[Android Asset Studio](https://romannurik.github.io/AndroidAssetStudio/icons-launcher.html)** - Upload 1 icon (512x512px recommended), download ALL sizes automatically!

**Other Good Options:**
- **[AppIcon.co](https://www.appicon.co/)** - Generates icons for Android & iOS
- **[Icon Kitchen](https://icon.kitchen/)** - Modern icon generator with effects
- **[Easyappicon](https://easyappicon.com/)** - Simple and fast

**Free Icon Sources (if you need an icon design):**
- **[Flaticon](https://www.flaticon.com/)** - Huge free icon library
- **[Icons8](https://icons8.com/)** - Free icons in any size
- **[Freepik](https://www.freepik.com/icons)** - Free vector icons
- **[Noun Project](https://thenounproject.com/)** - Simple icons (some free)
- **[Iconscout](https://iconscout.com/free-icons)** - Free icon collections

**Pro Tip:** Start with a high-quality icon (at least 512x512px) for best results!

---

### 🌐 5. Set Your Website URL

Search for: **`<WEBSITE_URL>`**

This is the website that will load in your app.

#### File 1: `app/src/main/java/com/example/app/MainActivity.java`

```java
// REMOTE RESOURCE
mWebView.loadUrl("https://kigemmanuel.github.io"); // <WEBSITE_URL> - Change this to your website URL
```

**What to do:** Replace `"https://kigemmanuel.github.io"` with your full website URL

**Example:**
```java
mWebView.loadUrl("https://www.mywebsite.com");
```

#### File 2: `app/src/main/java/com/example/app/MyWebViewClient.java`

```java
String hostname = "kigemmanuel.github.io"; // <WEBSITE_URL> - Change to your domain (no https://)
```

**What to do:** Replace with just your domain name (without `https://` or `www.`)

**Examples:**
- If your site is `https://www.mywebsite.com` → use `"mywebsite.com"`
- If your site is `https://myblog.github.io` → use `"myblog.github.io"`

**Why two files?** The first file loads your website. The second file keeps links inside your app and opens external links in the browser.

---

### 📱 6. Using Local HTML Files (Optional)

Want to bundle HTML files **inside** your app instead of loading from the internet?

Search for: **`<LOCAL_HTML>`**

1. **Put your files** in the `app/src/main/assets/` folder
   - Your main file should be named `index.html`
   - Include all CSS, JavaScript, images, etc.

2. **In MainActivity.java**, change these lines:

```java
// Comment out the remote URL:
// mWebView.loadUrl("https://kigemmanuel.github.io"); // <WEBSITE_URL>

// Uncomment the local file line:
mWebView.loadUrl("file:///android_asset/index.html"); // <LOCAL_HTML>
```

Now your app will load the local HTML instead of a website!

---

## 🛠️ Building Your App

You have **2 options** to build your app:

### Option 1: Build Locally (Requires Android Studio & Good PC)

**In Android Studio:**
1. Click **Build → Build Bundle(s) / APK(s) → Build APK(s)**
2. Wait for the build to finish
3. Click **locate** when it's done
4. Your APK is in `app/build/outputs/apk/debug/app-debug.apk`

**Using Terminal:**
```bash
# For testing on your device
./gradlew assembleDebug

# For Google Play Store
./gradlew bundleRelease
```

---

### Option 2: Build with GitHub Actions (NO PC NEEDED! 🎉)

**This is PERFECT if you don't have a powerful PC!** GitHub will build your app for FREE in the cloud.

#### First Time Setup:

1. **Fork this repository** on GitHub (click the Fork button)
2. **Enable GitHub Actions:**
   - Go to your forked repo
   - Click **Settings** tab
   - Click **Actions** in the left sidebar
   - Select **Allow all actions**
   - Click **Save**

#### Every Time You Make Changes:

**Step 1: Edit your files** (you can do this directly on GitHub!)
- Click on any file (like `strings.xml`)
- Click the pencil icon (Edit)
- Make your changes
- Click **Commit changes** at the bottom

**Step 2: Push your changes** (if editing locally)
```bash
git add .
git commit -m "Updated my app"
git push
```

**Step 3: Wait for the build** (takes 3-5 minutes)
- Go to the **Actions** tab in your repo
- You'll see your build running (yellow dot 🟡)
- Wait for it to turn green ✅

**Step 4: Download your APK & AAB**
- Click on the completed build
- Scroll down to **Artifacts**
- Download **app-debug-apk** (for testing on your phone)
- Download **app-release-aab** (for uploading to Play Store)

**That's it!** No Android Studio, no powerful PC needed! 🎉

---

### 🔄 Manual Build (Without Pushing Code)

Want to build without making code changes?

1. Go to **Actions** tab
2. Click **Android CI** on the left
3. Click **Run workflow** button
4. Select your branch
5. Click **Run workflow**
6. Wait and download artifacts!

---

## 📲 Testing Your App

### Install APK on Your Phone:

**Method 1: Via USB (Android Studio)**
1. Enable **Developer Options** on your phone
   - Go to **Settings → About Phone**
   - Tap **Build Number** 7 times
2. Enable **USB Debugging**
   - Go to **Settings → Developer Options**
   - Turn on **USB Debugging**
3. Connect phone to PC with USB cable
4. Click the green **Play** button in Android Studio

**Method 2: Install APK File Directly**
1. Download the APK (from GitHub Actions or your build folder)
2. Send the APK to your phone (via email, USB, cloud storage, etc.)
3. Open the APK file on your phone
4. Allow **Install from Unknown Sources** if asked
5. Tap **Install**
6. Test your app!

---

## 🎯 Quick Reference Table

| Search This | What It Does | Where to Find |
|------------|-------------|---------------|
| `<APPNAME>` | Your app's display name | `strings.xml` |
| `<PACKAGE_NAME>` | Unique app identifier (3 files) | `build.gradle`, `AndroidManifest.xml`, `MainActivity.java` |
| `<VERSION_CODE>` | Internal version number | `build.gradle` |
| `<VERSION_NAME>` | User-visible version | `build.gradle` |
| `<ICON>` | App icon images | All `mipmap-*` folders |
| `<WEBSITE_URL>` | Your website to load | `MainActivity.java`, `MyWebViewClient.java` |
| `<LOCAL_HTML>` | Local HTML file path | `MainActivity.java` |

---

## 🎓 Step-by-Step Checklist

Use this checklist to make sure you changed everything:

- [ ] Changed app name in `strings.xml`
- [ ] Changed package name in `build.gradle`
- [ ] Changed package name in `AndroidManifest.xml` (2 places)
- [ ] Changed package name in `MainActivity.java`
- [ ] Refactored/renamed folder structure to match package name
- [ ] Updated version code and version name
- [ ] Replaced app icons in all mipmap folders
- [ ] Changed website URL in `MainActivity.java`
- [ ] Changed domain in `MyWebViewClient.java`
- [ ] Tested build (locally or with GitHub Actions)
- [ ] Installed and tested APK on phone

---

## ⚠️ Common Issues & Solutions

### "Package name already exists"
**Problem:** Your package name isn't unique
**Solution:** Choose a different package name. Check Google Play Store to see if it's taken.

### "Build failed" in GitHub Actions
**Problem:** Syntax error or wrong file format
**Solution:** Check your changes. Make sure you didn't accidentally delete important code.

### "App won't install on phone"
**Problem:** Package name conflicts with existing app
**Solution:** Uninstall the old app first, or use a different package name.

### "White screen when opening app"
**Problem:** Wrong URL or no internet connection
**Solution:** Check your URL is correct. Make sure your phone has internet. Check AndroidManifest.xml has `<uses-permission android:name="android.permission.INTERNET" />`.

### "Icon not changing"
**Problem:** Old icons still cached
**Solution:** In Android Studio: **Build → Clean Project**, then **Build → Rebuild Project**

### "External links open in the app"
**Problem:** Wrong hostname in MyWebViewClient.java
**Solution:** Make sure the hostname matches your website's domain exactly.

---

## 🚀 Publishing to Google Play Store

Ready to publish? Here's a quick overview:

1. **Build a signed AAB** (App Bundle)
   - In Android Studio: **Build → Generate Signed Bundle**
   - Create a keystore (save it safely!)
   - Build release bundle

2. **Create a Play Console account** ([play.google.com/console](https://play.google.com/console))
   - One-time fee of $25

3. **Prepare your assets:**
   - App icon (512x512px)
   - Feature graphic (1024x500px)
   - Screenshots (at least 2, portrait and landscape)
   - Short description (80 characters)
   - Full description (4000 characters)
   - Privacy policy URL (required!)

4. **Upload your AAB** and complete the store listing

5. **Submit for review** (usually takes 1-3 days)

**Note:** This is a simplified overview. Google has detailed guides in Play Console.

---

## 🙏 Credits & Thanks

- Original template by **[slymax/webview](https://github.com/slymax/webview)** - Thanks for the awesome base!
- Modified and enhanced with easy customization tags and GitHub Actions workflow
- Made with ❤️ for developers who want to build apps quickly

---

## 💬 Need Help?

Having issues? Here's what to do:

1. **Read the error message** carefully - it usually tells you what's wrong
2. **Check this README** - most common issues are covered here
3. **Search existing issues** on GitHub
4. **Open a new issue** with:
   - What you're trying to do
   - What error you're getting
   - Screenshots if possible
   - What you've already tried

We're here to help! 🤝

---

## 📄 License

This project is open source and available under the MIT License. Feel free to use it, modify it, and share it!

---

## ⭐ Show Some Love

If this template helped you build your app, please:
- ⭐ **Star this repository** on GitHub
- 🍴 **Share it** with others who might find it useful
- 📣 **Tell your friends** about it

---

**Happy App Building! 🚀📱**

*Remember: You don't need to be a Java expert or have a powerful PC. Just follow the steps, use the search tags, and let GitHub Actions do the heavy lifting!*