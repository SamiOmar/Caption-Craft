# ⚙️ Caption Craft - Complete Configuration Guide

**Step-by-step instructions for CodeCanyon buyers to configure and customize the app**

---

## 🚀 PART 1: Essential Configuration (REQUIRED)

### 📁 **File Structure Overview**
```
CaptionCraft/
├── CaptionCraft.xcodeproj          ← Main Xcode project
├── CaptionCraft/
│   ├── Info.plist                  ← ⚠️ EDIT: AdMob App ID
│   ├── Utils/
│   │   └── Constants.swift         ← ⚠️ EDIT: Ad Unit IDs, App Settings
│   ├── Services/
│   │   └── AdService.swift         ← AdMob implementation (no changes needed)
│   ├── Views/
│   │   └── ExportView.swift        ← Ad integration (no changes needed)
│   └── Assets.xcassets/
│       └── AppIcon.appiconset/     ← ⚠️ EDIT: Replace app icon
```

---

## 📱 **STEP 1: Basic App Configuration**

### 1.1 Change App Name and Bundle ID

**📍 Location:** Xcode Project Settings
```
1. Open CaptionCraft.xcodeproj in Xcode
2. Click on "CaptionCraft" project (blue icon) in left sidebar
3. Select "CaptionCraft" target
4. Go to "General" tab
5. Change these fields:
```

**⚙️ Required Changes:**
```
Display Name: "Your App Name"
Bundle Identifier: com.yourcompany.yourappname
Version: 1.0
Build: 1
```

### 1.2 Set Development Team

**📍 Location:** Xcode Project Settings → Signing & Capabilities
```
1. Still in project settings
2. Go to "Signing & Capabilities" tab
3. Under "Team" dropdown:
   - Select your Apple Developer team
   - If not visible, add account in Xcode → Preferences → Accounts
```

---

## 💰 **STEP 2: AdMob Configuration (REQUIRED FOR MONETIZATION)**

### 2.1 Get Your AdMob IDs

**Before configuring the app, you need:**
1. **AdMob App ID** (format: `ca-app-pub-1234567890123456~1234567890`)
2. **Rewarded Ad Unit ID** (format: `ca-app-pub-1234567890123456/1234567890`)

**How to get these:**
```
1. Go to https://admob.google.com
2. Create account and verify
3. Click "Apps" → "Add App" → iOS
4. Enter app name, get APP ID
5. Click "Ad units" → "Add ad unit" → "Rewarded"
6. Name it "Premium Export", get AD UNIT ID
```

### 2.2 Configure Info.plist

**📍 File:** `CaptionCraft/Info.plist`

**🔍 Find this line:**
```xml
<key>GADApplicationIdentifier</key>
<string>ca-app-pub-6969174555160998~5410990496</string>
```

**✏️ Replace with YOUR AdMob App ID:**
```xml
<key>GADApplicationIdentifier</key>
<string>ca-app-pub-YOUR-APP-ID-HERE~YOUR-APP-NUMBER</string>
```

### 2.3 Configure Constants.swift

**📍 File:** `CaptionCraft/Utils/Constants.swift`

**🔍 Find the Ads struct (around line 284):**
```swift
struct Ads {
    static let useMock: Bool = false
    static let mockWatchSeconds: Double = 5
    static let rewardedAdUnitID: String = "ca-app-pub-6969174555160998/8145783284"
    static let testRewardedAdUnitID: String = "ca-app-pub-6969174555160998/8145783284"
    static let debugLoggingEnabled: Bool = true
    static let fallbackToDirectExport: Bool = true
}
```

**✏️ Replace with YOUR Ad Unit IDs:**
```swift
struct Ads {
    static let useMock: Bool = false
    static let mockWatchSeconds: Double = 5
    static let rewardedAdUnitID: String = "ca-app-pub-YOUR-AD-UNIT-ID-HERE"
    static let testRewardedAdUnitID: String = "ca-app-pub-3940256099942544/1712485313" // Keep Google's test ID
    static let debugLoggingEnabled: Bool = true
    static let fallbackToDirectExport: Bool = true
}
```

### 2.4 Update Xcode Project Settings (AdMob App ID)

**📍 Location:** Xcode Project Settings → Info
```
1. Select CaptionCraft project → CaptionCraft target
2. Go to "Info" tab
3. Find "GADApplicationIdentifier" in the list
4. Double-click the value field
5. Replace with your AdMob App ID
```

---

## 🎨 **STEP 3: App Customization**

### 3.1 Change App Icon

**📍 Location:** `CaptionCraft/Assets.xcassets/AppIcon.appiconset/`

**📋 Required Icon Sizes:**
```
- 1024x1024px (App Store)
- 180x180px (iPhone)
- 120x120px (iPhone)
- 167x167px (iPad Pro)
- 152x152px (iPad)
- 76x76px (iPad)
```

**🔧 How to Replace:**
```
1. Open CaptionCraft.xcodeproj
2. Navigate to Assets.xcassets in left sidebar
3. Click on "AppIcon"
4. Drag your icon files to corresponding size slots
5. Or use online tools like "Icon Set Creator"
```

### 3.2 Change App Colors and Branding

**📍 File:** `CaptionCraft/Utils/Constants.swift`

**🔍 Find UI Colors struct (around line 252):**
```swift
struct Colors {
    static let primary = Color(hex: "007AFF")
    static let secondary = Color(hex: "5856D6")
    static let accent = Color(hex: "007AFF")
    static let success = Color(hex: "34C759")
    static let warning = Color(hex: "FF9500")
    static let error = Color(hex: "FF3B30")
    // ... more colors
}
```

**✏️ Customize Your Brand Colors:**
```swift
struct Colors {
    static let primary = Color(hex: "FF6B35")      // Your main brand color
    static let secondary = Color(hex: "004E89")    // Your secondary color
    static let accent = Color(hex: "FF6B35")       // Accent (usually same as primary)
    static let success = Color(hex: "00C851")      // Keep or customize
    static let warning = Color(hex: "FF8800")      // Keep or customize
    static let error = Color(hex: "FF4444")        // Keep or customize
}
```

### 3.3 Customize App Settings

**📍 File:** `CaptionCraft/Utils/Constants.swift`

**🔍 Find App struct (around line 5):**
```swift
struct App {
    static let name = "Caption Craft"
    static let version = "1.0.0"
    static let bundleIdentifier = "com.captioncraft.app"
}
```

**✏️ Update with Your App Info:**
```swift
struct App {
    static let name = "Your App Name"
    static let version = "1.0.0"
    static let bundleIdentifier = "com.yourcompany.yourapp"
}
```

### 3.4 Configure Video Settings

**📍 File:** `CaptionCraft/Utils/Constants.swift`

**🔍 Find Video struct (around line 11):**
```swift
struct Video {
    static let maxFileSize: Int64 = 500 * 1024 * 1024 // 500 MB
    static let maxDuration: TimeInterval = 600 // 10 minutes
    static let supportedFormats = ["mp4", "mov", "avi", "mkv", "m4v"]
    static let minDuration: TimeInterval = 1 // 1 second
}
```

**✏️ Customize if needed:**
```swift
struct Video {
    static let maxFileSize: Int64 = 1000 * 1024 * 1024 // 1 GB (if you want larger files)
    static let maxDuration: TimeInterval = 1200 // 20 minutes (if you want longer videos)
    static let supportedFormats = ["mp4", "mov"] // Remove formats you don't want
    static let minDuration: TimeInterval = 3 // 3 seconds minimum
}
```

---

## 📧 **STEP 4: Contact Information**

### 4.1 Update Support Email

**📍 Files to update:**
- `CaptionCraft/Views/PrivacyPolicyView.swift`
- `CaptionCraft/Views/TermsOfServiceView.swift`
- Website files (privacy.html, terms.html)

**🔍 Find and replace in all files:**
```
Old: sami.dev.studioo@gmail.com
New: your-support-email@gmail.com
```

**💡 Easy way to find all instances:**
```
1. In Xcode: Edit → Find → Find in Project (Cmd+Shift+F)
2. Search for: "sami.dev.studioo@gmail.com"
3. Replace all with your email
```

---

## 🏪 **STEP 5: App Store Preparation**

### 5.1 App Store Connect Setup

**📋 Required Information:**
```
App Name: Your App Name
SKU: yourapp-ios-2024
Bundle ID: com.yourcompany.yourapp (same as Xcode)
Primary Language: English
```

### 5.2 App Description Template

**Copy this and customize:**
```
Transform your videos with professional AI-generated subtitles in seconds!

🎬 FEATURES:
• AI-powered speech recognition with 95%+ accuracy
• Support for 50+ languages worldwide
• Beautiful, customizable subtitle styles
• Privacy-first: all processing on your device
• Export in HD quality for social media
• Completely free with no hidden costs

🚀 PERFECT FOR:
• Content creators and influencers
• Social media marketers
• Educators and trainers
• Making videos accessible

✨ HOW IT WORKS:
1. Import or record your video
2. AI creates subtitles automatically
3. Customize style and edit text
4. Export your captioned video

🔒 PRIVACY GUARANTEED:
Your videos are processed entirely on your device. No uploads, no cloud storage, complete privacy.

Download now and make your videos accessible to everyone!
```

### 5.3 App Store Screenshots

**📱 Required Screenshots:**
```
iPhone (1290x2796 pixels):
- Main screen with video selection
- Transcription in progress
- Subtitle editing interface
- Style customization
- Final exported video

iPad (2048x2732 pixels) - Optional:
- Same screens optimized for tablet
```

### 5.4 App Store Keywords

**📝 Recommended Keywords:**
```
subtitles,captions,video,AI,speech recognition,accessibility,social media,content creator,transcription,automatic
```

---

## 🧪 **STEP 6: Testing Configuration**

### 6.1 Test AdMob Integration

**🔧 Testing Steps:**
```
1. Build app on physical iOS device (ads don't work in simulator)
2. Import a video
3. Go through transcription process
4. Try to export video
5. Tap "Watch Ad to Export"
6. Verify ad loads and plays
7. Confirm export works after ad
```

**🐛 If ads don't load:**
```
Check Xcode console for errors like:
- "AdMob Error: No ad to show"
- "AdMob Error Code: 1" (No fill)
- "AdMob Error: Request Error"

Solutions:
- Verify AdMob App ID in Info.plist
- Check Ad Unit ID in Constants.swift
- Wait 24-48 hours for AdMob approval
- Test with different geographic location
```

### 6.2 Test Core Functionality

**📋 Testing Checklist:**
```
✅ App builds and runs without crashes
✅ Video import from photo library works
✅ Speech recognition creates subtitles (test on device)
✅ Manual subtitle editing works
✅ Style customization applies correctly
✅ Video export saves to photo library
✅ Share functionality works
✅ AdMob ads load and reward works
✅ Settings screens display correctly
✅ Privacy policy and terms load
```

---

## 🔧 **STEP 7: Advanced Customization (OPTIONAL)**

### 7.1 Add Custom Subtitle Styles

**📍 File:** `CaptionCraft/Utils/Constants.swift`

**🔍 Find presetStyles array (around line 187):**
```swift
static let presetStyles: [CaptionStyle] = [
    CaptionStyle(
        name: "Classic",
        font: .system,
        fontSize: 24,
        textColor: .white,
        backgroundColor: .black,
        borderColor: .black,
        borderWidth: 2,
        position: .bottom,
        maxLines: 2,
        videoSize: CGSize(width: 1920, height: 1080),
        textBackgroundCornerRadius: 8,
        highlightBackgroundCornerRadius: 8
    ),
    // ... more styles
]
```

**✏️ Add your custom style:**
```swift
CaptionStyle(
    name: "Your Custom Style",
    font: .system,
    fontSize: 26,                    // Larger text
    textColor: .blue,               // Blue text
    backgroundColor: .yellow,        // Yellow background
    borderColor: .black,
    borderWidth: 3,                 // Thicker border
    position: .center,              // Center position
    maxLines: 1,                    // Single line
    videoSize: CGSize(width: 1920, height: 1080),
    textBackgroundCornerRadius: 15,
    highlightBackgroundCornerRadius: 15
),
```

### 7.2 Modify Supported Languages

**📍 File:** `CaptionCraft/Utils/Constants.swift`

**🔍 Find supportedLanguages dictionary (around line 27):**
```swift
static let supportedLanguages: [String: String] = [
    "en-US": "English (US)",
    "de-DE": "Deutsch",
    "fr-FR": "Français",
    // ... many more languages
]
```

**✏️ Remove languages you don't want:**
```swift
// Comment out or remove unwanted languages
// "zh-CN": "中文 (简体)",  // Remove Chinese
// "ar-SA": "العربية",      // Remove Arabic
```

**✏️ Add new languages:**
```swift
"pt-PT": "Português",
"nl-NL": "Nederlands",
"sv-SE": "Svenska",
```

---

## 📋 **STEP 8: Final Checklist Before App Store Submission**

### 8.1 Code Configuration
```
✅ Bundle ID changed to your unique identifier
✅ App name updated in project settings
✅ Development team selected
✅ AdMob App ID updated in Info.plist
✅ AdMob Ad Unit ID updated in Constants.swift
✅ App icon replaced with your design
✅ Brand colors updated in Constants.swift
✅ Support email updated throughout app
✅ App tested on physical device
✅ AdMob integration tested and working
```

### 8.2 App Store Assets
```
✅ App icon (1024x1024) prepared
✅ iPhone screenshots taken
✅ App description written
✅ Keywords selected
✅ Privacy policy URL ready
✅ Support URL ready
✅ App Store Connect app created
✅ All metadata filled in
```

### 8.3 AdMob Readiness
```
✅ AdMob account fully verified
✅ Payment information added to AdMob
✅ App created in AdMob console
✅ Rewarded ad unit created
✅ Production ad IDs configured in app
✅ Test ads working on device
✅ Ready to switch to production ads
```

---

## 🚨 **IMPORTANT NOTES**

### ⚠️ **Don't Skip These:**
1. **ALWAYS test on physical device** - Simulator doesn't show ads or speech recognition
2. **Use test Ad Unit IDs during development** - Switch to production before App Store submission
3. **Complete AdMob account setup** - Add payment info or ads won't serve
4. **Update all email addresses** - Replace with your support email
5. **Test export functionality** - Ensure videos save to photo library

### 🔒 **Privacy Compliance:**
- App processes videos locally (privacy-first)
- No personal data collected
- AdMob may collect device advertising ID
- Privacy policy included and linked

### 💡 **Pro Tips:**
- Test app thoroughly before submission
- Use unique, descriptive app name
- Optimize for App Store search with good keywords
- Monitor AdMob performance after launch
- Respond to user reviews promptly

---

## 🆘 **Getting Help**

### If you encounter issues:
1. **Check this guide first** - Most issues covered here
2. **Review error messages** - Xcode console shows detailed errors
3. **Test step by step** - Isolate the problem area
4. **Contact support**: sami.dev.studioo@gmail.com

### Common Issues:
- **Build errors**: Usually bundle ID or team selection
- **Ad issues**: Usually incorrect AdMob configuration
- **Crashes**: Usually missing permissions or device testing needed

---

**🎉 You're ready to launch your Caption Craft app! Follow this guide step by step, and you'll have a working, monetized app ready for the App Store.**