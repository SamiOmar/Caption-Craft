# 📝 Required File Changes - Caption Craft Configuration

**Exact files and code changes needed to customize your app**

---

## 🚨 CRITICAL: Files You MUST Edit

### 1️⃣ **Info.plist** - AdMob App ID
```
📁 File: CaptionCraft/Info.plist
🔍 Line: 6
```

**FIND THIS:**
```xml
<key>GADApplicationIdentifier</key>
<string>ca-app-pub-6969174555160998~5410990496</string>
```

**CHANGE TO:**
```xml
<key>GADApplicationIdentifier</key>
<string>YOUR_ADMOB_APP_ID_HERE</string>
```

**Example:**
```xml
<key>GADApplicationIdentifier</key>
<string>ca-app-pub-1234567890123456~1234567890</string>
```

---

### 2️⃣ **Constants.swift** - Ad Unit IDs and App Settings
```
📁 File: CaptionCraft/Utils/Constants.swift
🔍 Lines: 284-291
```

**FIND THIS:**
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

**CHANGE TO:**
```swift
struct Ads {
    static let useMock: Bool = false
    static let mockWatchSeconds: Double = 5
    static let rewardedAdUnitID: String = "YOUR_AD_UNIT_ID_HERE"
    static let testRewardedAdUnitID: String = "ca-app-pub-3940256099942544/1712485313"
    static let debugLoggingEnabled: Bool = true
    static let fallbackToDirectExport: Bool = true
}
```

**Example:**
```swift
struct Ads {
    static let useMock: Bool = false
    static let mockWatchSeconds: Double = 5
    static let rewardedAdUnitID: String = "ca-app-pub-1234567890123456/1234567890"
    static let testRewardedAdUnitID: String = "ca-app-pub-3940256099942544/1712485313"
    static let debugLoggingEnabled: Bool = true
    static let fallbackToDirectExport: Bool = true
}
```

---

## 🎨 RECOMMENDED: Branding Customization

### 3️⃣ **Constants.swift** - App Information
```
📁 File: CaptionCraft/Utils/Constants.swift
🔍 Lines: 5-9
```

**FIND THIS:**
```swift
struct App {
    static let name = "Caption Craft"
    static let version = "1.0.0"
    static let bundleIdentifier = "com.captioncraft.app"
}
```

**CHANGE TO:**
```swift
struct App {
    static let name = "Your App Name"
    static let version = "1.0.0"
    static let bundleIdentifier = "com.yourcompany.yourapp"
}
```

---

### 4️⃣ **Constants.swift** - Brand Colors
```
📁 File: CaptionCraft/Utils/Constants.swift
🔍 Lines: 252-266
```

**FIND THIS:**
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

**CHANGE TO YOUR BRAND COLORS:**
```swift
struct Colors {
    static let primary = Color(hex: "FF6B35")      // Your main brand color
    static let secondary = Color(hex: "004E89")    // Your secondary color
    static let accent = Color(hex: "FF6B35")       // Usually same as primary
    static let success = Color(hex: "00C851")      // Keep or customize
    static let warning = Color(hex: "FF8800")      // Keep or customize
    static let error = Color(hex: "FF4444")        // Keep or customize
    // ... keep other colors unchanged
}
```

---

## 📧 IMPORTANT: Contact Information

### 5️⃣ **Multiple Files** - Support Email
```
🔍 Search for: sami.dev.studioo@gmail.com
📁 Replace in ALL files with your email
```

**Files containing email:**
- `index.html`
- `privacy.html`
- `terms.html`
- `CONFIGURATION_GUIDE.md`
- `ADMOB_SETUP.md`

**How to replace all at once:**
```
1. In Xcode: Edit → Find → Find in Project (Cmd+Shift+F)
2. Search: sami.dev.studioo@gmail.com
3. Replace: your-support-email@gmail.com
4. Click "Replace All"
```

---

## 🏪 Xcode Project Settings

### 6️⃣ **Bundle Identifier**
```
📍 Location: Xcode Project Settings
🎯 Target: CaptionCraft
📋 Tab: General
```

**CHANGE THESE:**
```
Display Name: Your App Name
Bundle Identifier: com.yourcompany.yourapp
Version: 1.0
Build: 1
Team: Select your Apple Developer team
```

### 7️⃣ **AdMob App ID in Xcode**
```
📍 Location: Xcode Project Settings
🎯 Target: CaptionCraft
📋 Tab: Info
```

**FIND:**
```
GADApplicationIdentifier: ca-app-pub-6969174555160998~5410990496
```

**CHANGE TO:**
```
GADApplicationIdentifier: YOUR_ADMOB_APP_ID_HERE
```

---

## 🎨 OPTIONAL: Advanced Customization

### 8️⃣ **App Icon**
```
📁 Location: CaptionCraft/Assets.xcassets/AppIcon.appiconset/
🖼️ Replace: All app icon sizes with your design
```

**Required Sizes:**
- 1024x1024 (App Store)
- 180x180 (iPhone 3x)
- 120x120 (iPhone 2x)
- 167x167 (iPad Pro)
- 152x152 (iPad 2x)
- 76x76 (iPad 1x)

### 9️⃣ **Subtitle Styles** (Optional)
```
📁 File: CaptionCraft/Utils/Constants.swift
🔍 Lines: 187-230
```

**Add custom styles to the presetStyles array:**
```swift
CaptionStyle(
    name: "Your Custom Style",
    font: .system,
    fontSize: 26,
    textColor: .blue,
    backgroundColor: .yellow,
    borderColor: .black,
    borderWidth: 3,
    position: .center,
    maxLines: 1,
    videoSize: CGSize(width: 1920, height: 1080),
    textBackgroundCornerRadius: 15,
    highlightBackgroundCornerRadius: 15
),
```

### 🔟 **Video Settings** (Optional)
```
📁 File: CaptionCraft/Utils/Constants.swift
🔍 Lines: 11-16
```

**Modify video constraints:**
```swift
struct Video {
    static let maxFileSize: Int64 = 1000 * 1024 * 1024  // 1GB instead of 500MB
    static let maxDuration: TimeInterval = 1200         // 20 minutes instead of 10
    static let supportedFormats = ["mp4", "mov"]        // Remove formats you don't want
    static let minDuration: TimeInterval = 3            // 3 seconds minimum
}
```

---

## ✅ Configuration Checklist

### **REQUIRED Changes (App Won't Work Without These):**
- [ ] AdMob App ID in Info.plist
- [ ] AdMob Ad Unit ID in Constants.swift
- [ ] Bundle Identifier in Xcode project settings
- [ ] Apple Developer Team selection

### **RECOMMENDED Changes (For Your Branding):**
- [ ] App name in project settings
- [ ] App icon replacement
- [ ] Brand colors in Constants.swift
- [ ] Support email addresses

### **OPTIONAL Changes (For Customization):**
- [ ] App information in Constants.swift
- [ ] Custom subtitle styles
- [ ] Video processing settings
- [ ] Additional language support

---

## 🚨 Critical Notes

### **⚠️ Don't Change These Files:**
- `AdService.swift` - AdMob implementation (working correctly)
- `ExportView.swift` - Ad integration logic (working correctly)
- Any files in `Services/` folder unless you know what you're doing

### **⚠️ Testing Requirements:**
- **ALWAYS test on physical iOS device** (simulator doesn't show ads)
- Test with test Ad Unit IDs first, then switch to production
- Verify video export and ad completion flow

### **⚠️ Before App Store Submission:**
- Switch from test to production Ad Unit IDs
- Test all functionality on device
- Verify AdMob account is fully set up with payment info
- Test ad loading and reward completion

---

## 📞 Need Help?

If you get stuck on any of these changes:

1. **Check the full CONFIGURATION_GUIDE.md** for detailed explanations
2. **Review ADMOB_SETUP.md** for AdMob-specific issues
3. **Contact support:** sami.dev.studioo@gmail.com

**Most common issues:**
- Forgetting to change Bundle ID → Build errors
- Wrong AdMob IDs → Ads don't load
- Testing in simulator → Nothing works (use device!)
- Missing Apple Developer team → Can't build

---

**🎉 Follow this checklist exactly, and your app will be ready for the App Store!**