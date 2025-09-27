# Caption Craft - Complete Documentation

🎬 **Professional iOS Video Subtitle App - CodeCanyon Package**

## 📋 Table of Contents

1. [Quick Start](#-quick-start)
2. [AdMob Configuration](#-admob-configuration)
3. [App Customization](#-app-customization)
4. [App Store Submission](#-app-store-submission)
5. [Troubleshooting](#-troubleshooting)
6. [Advanced Features](#-advanced-features)
7. [Support](#-support)

---

## 🚀 Quick Start

### Prerequisites
- **Xcode 15.0** or later
- **iOS 14.0** deployment target
- **Apple Developer Account** (for App Store submission)
- **AdMob Account** (for monetization)

### 1. Initial Setup (5 minutes)

#### Step 1: Open the Project
```bash
1. Extract the downloaded ZIP file
2. Navigate to the iOS app folder
3. Double-click CaptionCraft.xcodeproj
4. Wait for Xcode to load the project
```

#### Step 2: Configure Bundle Identifier
```bash
1. Select CaptionCraft project in navigator
2. Select CaptionCraft target
3. Go to "Signing & Capabilities" tab
4. Change Bundle Identifier to: com.yourcompany.captioncraft
5. Select your development team
```

#### Step 3: Test the App
```bash
1. Select iPhone simulator (iPhone 14 Pro recommended)
2. Press Cmd+R to build and run
3. Test basic functionality:
   - Video import
   - Transcription (will use test data in simulator)
   - Style selection
   - Export process
```

### 2. First Build Success ✅
If the app builds and runs without errors, you're ready for customization!

---

## 💰 AdMob Configuration

### Step 1: Create AdMob Account
1. Go to [https://admob.google.com](https://admob.google.com)
2. Sign in with Google account
3. Click "Get Started" and accept terms
4. Create your first app

### Step 2: Generate App ID and Ad Unit ID

#### Create App in AdMob:
```
1. Click "Apps" in sidebar
2. Click "Add App"
3. Select "iOS"
4. Enter app name: "Caption Craft"
5. Copy the App ID (format: ca-app-pub-XXXXXXXXXXXXXXXX~XXXXXXXXXX)
```

#### Create Rewarded Ad Unit:
```
1. Click on your app name
2. Click "Ad Units" tab
3. Click "Add Ad Unit"
4. Select "Rewarded"
5. Enter ad unit name: "Premium Export Reward"
6. Copy the Ad Unit ID (format: ca-app-pub-XXXXXXXXXXXXXXXX/XXXXXXXXXX)
```

### Step 3: Update App Configuration

#### Update Info.plist:
```xml
<!-- File: CaptionCraft/Info.plist -->
<key>GADApplicationIdentifier</key>
<string>YOUR_ADMOB_APP_ID_HERE</string>
```

#### Update Constants.swift:
```swift
// File: CaptionCraft/Utils/Constants.swift
struct Ads {
    static let rewardedAdUnitID: String = "YOUR_AD_UNIT_ID_HERE"
    static let testRewardedAdUnitID: String = "YOUR_AD_UNIT_ID_HERE"
}
```

#### Update Xcode Project Settings:
```bash
1. Select CaptionCraft project
2. Select CaptionCraft target
3. Go to "Info" tab
4. Find "GADApplicationIdentifier"
5. Replace value with your App ID
```

### Step 4: Test AdMob Integration

#### For Simulator Testing:
```swift
// Keep test IDs for simulator testing
static let testRewardedAdUnitID: String = "ca-app-pub-3940256099942544/1712485313"
```

#### For Device Testing:
```swift
// Use your real Ad Unit ID
static let rewardedAdUnitID: String = "ca-app-pub-XXXXXXXXXXXXXXXX/XXXXXXXXXX"
```

### Step 5: Verify Integration
1. Build and run on device
2. Try to export a video
3. Tap "Watch Ad to Export"
4. Verify ad loads and plays
5. Confirm export works after ad completion

---

## 🎨 App Customization

### 1. Branding Customization

#### App Name:
```bash
1. Select CaptionCraft project
2. Select CaptionCraft target
3. Go to "Info" tab
4. Change "Display Name" to your app name
```

#### App Icon:
```bash
1. Prepare icon in all required sizes (use tools like Icon Set Creator)
2. Open CaptionCraft/Assets.xcassets
3. Click on AppIcon
4. Replace all icon sizes with your design
```

#### Color Scheme:
```swift
// File: CaptionCraft/Utils/Constants.swift
struct UI {
    struct Colors {
        static let primary = Color(hex: "007AFF")      // Main brand color
        static let secondary = Color(hex: "5856D6")    // Secondary color
        static let accent = Color(hex: "007AFF")       // Accent color
        static let success = Color(hex: "34C759")      // Success color
        static let warning = Color(hex: "FF9500")      // Warning color
        static let error = Color(hex: "FF3B30")        // Error color
    }
}
```

### 2. Feature Customization

#### Subtitle Styles:
```swift
// File: CaptionCraft/Utils/Constants.swift
static let presetStyles: [CaptionStyle] = [
    CaptionStyle(
        name: "Your Style Name",
        font: .system,
        fontSize: 24,
        textColor: .white,
        backgroundColor: .black,
        borderColor: .black,
        borderWidth: 2,
        position: .bottom,
        maxLines: 2
    )
]
```

#### Supported Languages:
```swift
// File: CaptionCraft/Utils/Constants.swift
// Enable/disable languages by commenting out entries
static let supportedLanguages: [String: String] = [
    "en-US": "English (US)",
    "de-DE": "German",
    "fr-FR": "French",
    // Add or remove languages as needed
]
```

#### Video Constraints:
```swift
// File: CaptionCraft/Utils/Constants.swift
struct Video {
    static let maxFileSize: Int64 = 500 * 1024 * 1024  // 500 MB
    static let maxDuration: TimeInterval = 600          // 10 minutes
    static let supportedFormats = ["mp4", "mov", "avi", "mkv", "m4v"]
}
```

### 3. UI Customization

#### Text Changes:
```swift
// File: CaptionCraft/Views/VideoUploadView.swift
// Search for user-facing text and update:
Text("Select a video to add subtitles")
Text("Choose from gallery or record new")
// Update these strings throughout the app
```

#### Layout Adjustments:
```swift
// File: CaptionCraft/Utils/Constants.swift
struct Layout {
    static let defaultPadding: CGFloat = 16
    static let cornerRadius: CGFloat = 12
    static let buttonHeight: CGFloat = 50
}
```

---

## 📱 App Store Submission

### 1. Prepare App Store Assets

#### App Icon:
- **Required Sizes**: 1024x1024 (App Store), 180x180 (iPhone), 120x120 (iPhone)
- **Format**: PNG without transparency
- **Design**: Simple, recognizable, works at small sizes

#### Screenshots:
- **iPhone**: 1290x2796 (iPhone 14 Pro) or 1242x2688 (iPhone 11 Pro Max)
- **iPad**: 2048x2732 (12.9-inch) recommended
- **Quantity**: 3-10 screenshots showing key features

#### App Preview Video (Optional):
- **Length**: 15-30 seconds
- **Resolution**: Same as screenshot requirements
- **Content**: Show core functionality and user flow

### 2. App Store Connect Setup

#### Create App Record:
```
1. Go to appstoreconnect.apple.com
2. Click "My Apps" → "+" → "New App"
3. Fill in app information:
   - Platform: iOS
   - Name: Your App Name
   - Primary Language: English
   - Bundle ID: com.yourcompany.captioncraft
   - Sku: Your unique identifier
```

#### App Information:
```
Name: Your App Name
Subtitle: AI Video Subtitles
Category: Photo & Video
Content Rights: Yes (you have rights to content)
Age Rating: 4+ (no inappropriate content)
```

#### Pricing:
```
Price: Free
Availability: All countries
```

### 3. Metadata and Description

#### App Description Template:
```
Create professional subtitles for your videos automatically with AI-powered speech recognition.

KEY FEATURES:
• AI-powered speech recognition with 95%+ accuracy
• Support for 50+ languages and dialects
• Customizable subtitle styles and fonts
• Local processing - your videos stay private
• Export in high quality for social media
• Completely free with no hidden costs

PERFECT FOR:
• Content creators and influencers
• Social media marketers
• Educators and trainers
• Anyone making videos more accessible

HOW IT WORKS:
1. Import or record your video
2. AI automatically creates subtitles
3. Customize style and edit text
4. Export your finished video

PRIVACY FIRST:
All video processing happens locally on your device. Your videos never leave your phone, ensuring complete privacy and security.

Download now and make your videos accessible to everyone!
```

#### Keywords:
```
subtitles,captions,video,AI,speech,recognition,accessibility,social media,content creator,transcription
```

#### Support URL:
```
https://yourusername.github.io/Caption-Craft/
```

#### Privacy Policy URL:
```
https://yourusername.github.io/Caption-Craft/privacy.html
```

### 4. Build and Upload

#### Archive the App:
```bash
1. In Xcode, select "Any iOS Device (arm64)"
2. Go to Product → Archive
3. Wait for archive to complete
4. Click "Distribute App"
5. Select "App Store Connect"
6. Follow the upload wizard
```

#### Submit for Review:
```
1. In App Store Connect, go to your app
2. Click on version "Prepare for Submission"
3. Fill in all required information
4. Upload screenshots and metadata
5. Click "Submit for Review"
```

### 5. Review Process

#### Timeline:
- **Review Time**: Usually 24-48 hours
- **Approval Rate**: High (if following guidelines)
- **Common Issues**: Missing info, metadata inconsistencies

#### After Approval:
```
1. App will appear in "Ready for Sale" status
2. You can release immediately or schedule release
3. Monitor reviews and ratings
4. Respond to user feedback
```

---

## 🔧 Troubleshooting

### Common Build Issues

#### Issue: "GoogleMobileAds not found"
**Solution:**
```bash
1. File → Packages → Reset Package Caches
2. Clean build folder (Cmd+Shift+K)
3. Rebuild project (Cmd+B)
```

#### Issue: "Bundle identifier already exists"
**Solution:**
```bash
1. Change bundle identifier in project settings
2. Use format: com.yourcompany.yourappname
3. Ensure it's unique in App Store Connect
```

#### Issue: "Provisioning profile errors"
**Solution:**
```bash
1. Ensure you have Apple Developer account
2. Xcode → Preferences → Accounts → Download Manual Profiles
3. Select "Automatically manage signing"
```

### Runtime Issues

#### Issue: "Ads not loading"
**Solution:**
```swift
1. Check AdMob App ID in Info.plist
2. Verify Ad Unit ID in Constants.swift
3. Test with AdMob test IDs first
4. Check internet connection
5. Review AdMob console for errors
```

#### Issue: "Speech recognition not working"
**Solution:**
```bash
1. Test on physical device (doesn't work in simulator)
2. Grant microphone permissions
3. Check supported languages list
4. Ensure clear audio quality
```

#### Issue: "Video export failing"
**Solution:**
```swift
1. Check available storage space
2. Verify video format compatibility
3. Test with shorter videos first
4. Check error logs in Xcode console
```

### Performance Issues

#### Issue: "App running slowly"
**Solution:**
```swift
1. Test on actual device (simulator is slower)
2. Check memory usage in Xcode instruments
3. Optimize video processing in background
4. Reduce video resolution if needed
```

#### Issue: "High memory usage"
**Solution:**
```swift
1. Release video objects after processing
2. Use autoreleasepool for heavy operations
3. Process videos in chunks
4. Monitor memory in Xcode instruments
```

---

## 🔧 Advanced Features

### 1. Custom Speech Recognition

#### Alternative AI Services:
```swift
// File: CaptionCraft/Services/TranscriptionService.swift
// Replace Apple's Speech framework with:
// - Google Cloud Speech-to-Text
// - Amazon Transcribe
// - Microsoft Speech Services
// - OpenAI Whisper
```

#### Cloud Processing:
```swift
// Benefits:
// - Better accuracy
// - More languages
// - Faster processing
// - Reduced device load

// Considerations:
// - Privacy implications
// - Internet requirement
// - Processing costs
// - Latency
```

### 2. Advanced Monetization

#### Subscription Model:
```swift
// Add StoreKit framework
// Implement subscription tiers:
// - Basic: Free with ads
// - Pro: $2.99/month - No ads, premium styles
// - Enterprise: $9.99/month - Cloud processing, API access
```

#### In-App Purchases:
```swift
// One-time purchases:
// - Premium styles pack: $1.99
// - Language packs: $0.99 each
// - Export formats: $1.99
// - Cloud storage: $2.99
```

### 3. Analytics Integration

#### Firebase Analytics:
```swift
// Add Firebase SDK
// Track user behavior:
// - Video processing success rate
// - Most used features
// - User retention
// - Conversion rates
```

#### Custom Events:
```swift
// Track business metrics:
Analytics.logEvent("video_processed", parameters: [
    "duration": videoDuration,
    "language": selectedLanguage,
    "style": selectedStyle
])
```

### 4. Advanced UI Features

#### Dark Mode Support:
```swift
// File: CaptionCraft/Utils/Constants.swift
// Add dark mode color schemes
// Automatic system appearance following
```

#### iPad Support:
```swift
// Optimize for larger screens:
// - Split view controllers
// - Drag and drop
// - Multiple video preview
// - Professional timeline editor
```

#### Accessibility:
```swift
// VoiceOver support
// Dynamic Type scaling
// High contrast mode
// Voice control compatibility
```

---

## 🛟 Support

### Documentation Resources
- **Setup Guide**: Quick start instructions
- **API Reference**: Code documentation
- **Video Tutorials**: Visual setup guides
- **FAQ**: Common questions and answers

### Developer Support
- **Email**: sami.dev.studioo@gmail.com
- **Response Time**: 24-48 hours
- **Support Includes**: Setup help, customization guidance, bug fixes

### Community Resources
- **GitHub Issues**: Report bugs and request features
- **Stack Overflow**: Technical questions and solutions
- **iOS Developer Forums**: General iOS development help

### Update Policy
- **Regular Updates**: Bug fixes and improvements
- **iOS Compatibility**: Support for new iOS versions
- **Feature Requests**: Community-driven enhancements
- **Security Patches**: Timely security updates

---

## 📄 License & Legal

### Commercial License
- ✅ **Sell unlimited apps** with this source code
- ✅ **Modify and customize** as needed
- ✅ **White-label** for clients
- ✅ **No attribution required**

### Restrictions
- ❌ **Cannot resell source code** itself
- ❌ **Cannot create competing products** for sale
- ❌ **Must comply** with App Store guidelines
- ❌ **Cannot use** "Caption Craft" branding

### Third-Party Licenses
- **GoogleMobileAds**: Google's SDK license
- **Speech Framework**: Apple's framework license
- **AVFoundation**: Apple's framework license

---

*This documentation is comprehensive and covers everything needed to successfully launch your Caption Craft app. For additional support, contact the developer team.*