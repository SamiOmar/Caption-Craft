# AdMob Setup Guide

🎯 **Complete guide to configure AdMob monetization in Caption Craft**

## 📋 Overview

Caption Craft uses Google AdMob for monetization through rewarded video ads. Users watch an ad to unlock premium export features. This guide covers complete AdMob setup from account creation to live ads.

---

## 🚀 Step 1: Create AdMob Account

### 1.1 Sign Up for AdMob
```
1. Go to https://admob.google.com
2. Click "Get Started"
3. Sign in with your Google account
4. Accept AdMob Terms of Service
5. Complete account setup wizard
```

### 1.2 Verify Your Account
```
1. Provide tax information (if required)
2. Set up payment method
3. Verify phone number
4. Complete AdSense linking (if applicable)
```

---

## 📱 Step 2: Create iOS App in AdMob

### 2.1 Add New App
```
1. In AdMob dashboard, click "Apps" in sidebar
2. Click "Add App" button
3. Select "iOS" platform
4. Choose "No" for "Is your app listed on the App Store?" (initially)
5. Enter app details:
   - App name: "Caption Craft" (or your custom name)
   - Platform: iOS
```

### 2.2 App Configuration
```
After app creation, you'll receive:
- App ID: ca-app-pub-1234567890123456~1234567890
- Save this ID - you'll need it in your iOS project
```

---

## 🎬 Step 3: Create Rewarded Ad Unit

### 3.1 Create Ad Unit
```
1. Click on your app name in AdMob console
2. Go to "Ad units" tab
3. Click "Add ad unit"
4. Select "Rewarded" ad format
5. Configure ad unit:
   - Ad unit name: "Premium Export Reward"
   - Reward amount: 1
   - Reward item: "Premium Export"
```

### 3.2 Ad Unit Settings
```
Advanced settings (optional):
- Ad unit refresh rate: 60 seconds
- Show ads: Immediately
- User messaging: Default
- Close button delay: 5 seconds
```

### 3.3 Get Ad Unit ID
```
After creation, you'll receive:
- Ad Unit ID: ca-app-pub-1234567890123456/1234567890
- Save this ID for iOS integration
```

---

## 🔧 Step 4: Configure iOS Project

### 4.1 Update Info.plist
```xml
<!-- File: CaptionCraft/Info.plist -->
<!-- Find this key and update the value -->
<key>GADApplicationIdentifier</key>
<string>ca-app-pub-1234567890123456~1234567890</string>

<!-- Replace with YOUR AdMob App ID -->
```

### 4.2 Update Constants.swift
```swift
// File: CaptionCraft/Utils/Constants.swift
// Find the Ads struct and update:

struct Ads {
    static let useMock: Bool = false
    static let mockWatchSeconds: Double = 5

    // REPLACE WITH YOUR REAL AD UNIT ID
    static let rewardedAdUnitID: String = "ca-app-pub-1234567890123456/1234567890"

    // FOR TESTING: Use Google's test ad unit ID
    static let testRewardedAdUnitID: String = "ca-app-pub-3940256099942544/1712485313"

    static let debugLoggingEnabled: Bool = true
    static let fallbackToDirectExport: Bool = true
}
```

### 4.3 Update Xcode Project Settings
```
1. Open CaptionCraft.xcodeproj in Xcode
2. Select CaptionCraft project in navigator
3. Select CaptionCraft target
4. Go to "Info" tab
5. Find "GADApplicationIdentifier" key
6. Update value to your AdMob App ID
```

---

## 🧪 Step 5: Testing Configuration

### 5.1 Test with Google Test Ads
```swift
// For initial testing, use Google's test IDs:
static let testRewardedAdUnitID: String = "ca-app-pub-3940256099942544/1712485313"

// In your app, this will show test ads that don't generate revenue
// but allow you to test the integration
```

### 5.2 Testing Checklist
```
1. Build and run app on iOS device (simulator won't show ads)
2. Go through video export flow
3. Tap "Watch Ad to Export"
4. Verify test ad loads and plays
5. Confirm export works after ad completion
6. Check Xcode console for AdMob logs
```

### 5.3 Debug Logging
```swift
// Enable debug logging to see AdMob status:
// File: CaptionCraft/Services/AdService.swift

#if DEBUG
print("AdMob initialized with status: \(status)")
print("Loading rewarded ad with unit ID: \(adUnitId)")
print("AdMob configured for PRODUCTION ads")
#endif
```

---

## 🚀 Step 6: Production Configuration

### 6.1 Switch to Production Ads
```swift
// File: CaptionCraft/Utils/Constants.swift
// Change from test IDs to your real IDs:

static let rewardedAdUnitID: String = "ca-app-pub-YOUR-REAL-ID/YOUR-AD-UNIT-ID"

// Remove or comment out test configurations
```

### 6.2 Build Configuration
```swift
// The app automatically uses production ads in release builds
// Test ads only show in debug builds with test device IDs

#if DEBUG
// Test configuration
#else
// Production configuration
#endif
```

### 6.3 App Store Submission
```
1. Update app to use production AdMob IDs
2. Test on physical device with production ads
3. Submit to App Store with AdMob properly configured
4. After app approval, ads will start serving
```

---

## 💰 Step 7: AdMob Console Management

### 7.1 Monitor Performance
```
In AdMob console, track:
- Ad requests
- Fill rate
- eCPM (earnings per thousand impressions)
- Revenue
- User engagement
```

### 7.2 Optimize Ad Settings
```
1. Mediation: Add other ad networks for better fill rates
2. Ad formats: Experiment with different ad types
3. Frequency capping: Limit ads per user per day
4. Geographic targeting: Focus on high-value regions
```

### 7.3 Revenue Optimization
```
Best practices:
- Place ads at natural break points
- Don't force ads too frequently
- Provide clear value for watching ads
- Monitor user retention vs. revenue
```

---

## 🔍 Step 8: Troubleshooting

### 8.1 Common Issues

#### "No ads to show" Error
```
Causes:
- Incorrect Ad Unit ID
- App not approved in AdMob
- Low ad inventory
- Geographic restrictions

Solutions:
- Verify Ad Unit ID matches AdMob console
- Wait for AdMob approval (can take 24-48 hours)
- Test from different locations
- Check AdMob account status
```

#### Ads Not Loading
```
Causes:
- Internet connectivity issues
- AdMob account suspended
- App ID mismatch
- Test device not configured

Solutions:
- Check internet connection
- Verify AdMob account status
- Double-check App ID in Info.plist
- Use proper test device configuration
```

#### Revenue Not Showing
```
Causes:
- Using test ad IDs in production
- AdMob account not fully set up
- Payment information incomplete
- App not generating enough traffic

Solutions:
- Switch to production ad IDs
- Complete AdMob account setup
- Add payment method and tax info
- Increase app usage and ad impressions
```

### 8.2 Debug Tools

#### AdMob Test Console
```
1. Go to https://admob.google.com/home/
2. Navigate to "Test devices"
3. Add your iOS device ID for testing
4. Use test ads during development
```

#### Xcode Debug Output
```swift
// Check console for AdMob debug messages:
"AdMob initialized with status: Ready"
"Loading rewarded ad with unit ID: ca-app-pub-..."
"Ad loaded successfully"
"Ad failed to load with error: ..."
```

---

## 📈 Step 9: Advanced Configuration

### 9.1 Mediation Setup
```
1. In AdMob console, go to "Mediation"
2. Click "Create mediation group"
3. Add other ad networks (Facebook, Unity, etc.)
4. Set eCPM floors for optimization
5. Configure waterfall or bidding
```

### 9.2 User Consent (GDPR/CCPA)
```swift
// Add Google User Messaging Platform (UMP) SDK
// For apps serving ads in EU or California:

import UserMessagingPlatform

// Request consent before loading ads
UMPConsentForm.loadAndPresentIfRequired(from: viewController) { error in
    if error != nil {
        // Handle error
    } else {
        // Load ads after consent
    }
}
```

### 9.3 Analytics Integration
```swift
// Track ad performance with Firebase Analytics:

Analytics.logEvent("ad_impression", parameters: [
    "ad_platform": "admob",
    "ad_format": "rewarded",
    "ad_unit_name": "premium_export_reward"
])
```

---

## 📊 Expected Performance

### 9.1 Typical Metrics
```
- Fill Rate: 85-95% (varies by region)
- eCPM: $1-5 (depends on geography and audience)
- Click-through Rate: 3-8%
- Video Completion Rate: 80-95%
```

### 9.2 Revenue Estimation
```
Monthly Revenue = MAU × Ads per User × eCPM / 1000

Example:
- 10,000 monthly active users
- 2 ads per user per month
- $2 eCPM
- Revenue: 10,000 × 2 × $2 / 1000 = $40/month
```

---

## ✅ Final Checklist

Before going live:
- [ ] AdMob account fully set up with payment info
- [ ] iOS app created in AdMob console
- [ ] Rewarded ad unit created and configured
- [ ] App ID updated in Info.plist
- [ ] Ad Unit ID updated in Constants.swift
- [ ] Tested with production ads on real device
- [ ] Verified ad loading and completion flow
- [ ] Checked AdMob console for any warnings
- [ ] App submitted to App Store with correct configuration

---

**🎉 Congratulations!** Your AdMob integration is complete. Users can now watch ads to unlock premium features, and you'll start earning revenue from your app.

For support with AdMob setup, contact: sami.dev.studioo@gmail.com