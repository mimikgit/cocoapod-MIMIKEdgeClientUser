# MIMIKEdgeClientUser

MIMIKEdgeClientUser service library can help you interact with the following mimik services:

 * `Profile`
 * `Peer`
 * `Thumbnail`
 * `Places`

using these APIs:

### Profile

 * `userProfile`
 * `updateUserProfile`
 * `addUserProfileNotificationsConsent`
 * `deleteUserProfileNotificationsConsent`
 * `updateUserProfileAttributes`
 * `updateUserProfileProperties`
 * `updateUserSSN`
 * `findUserWith`

### Peer
 
 * `friends`
 * `friendList`
 * `receivedFriendRequests`
 * `receivedFriendRequestList`
 * `sentFriendRequests`
 * `sentFriendRequestList`
 * `requestFriendship`
 * `acceptFriendship`
 * `cancelFriendship`

### Thumbnail
 
 * `userAvatarLegacy`
 * `updateUserAvatarLegacy`
 * `userAvatarLegacyAttribute`

### Places
 
 * `addressSuggestions`
 * `places`

Please see the in-code documentation in Xcode for more details.

## Supported Platforms, Targets
* `iOS Devices running iOS 14+`
* `iOS Simulators running iOS 14+`
* `iOS Mac Catalyst running macOS 12.0`

## Requirements
```
iOS 14.0+
MIMIKEdgeClientCore
```

## Installation

To install it, simply add the following lines to your Podfile:

For Xcode 13.4.x compatibility

```swift
platform :ios, '14.0'
source 'https://github.com/CocoaPods/Specs.git'
source 'https://github.com/mimikgit/cocoapod-edge-specs.git'

use_frameworks!
inhibit_all_warnings!

def mimik
  pod 'MIMIKEdgeClientCore', '13.6.0'
  pod 'MIMIKEdgeClientUser', '13.6.0'
end

target '{target}' do
  mimik()
end

post_install do |installer|
  installer.pods_project.targets.each do |target|
    target.build_configurations.each do |config|
      config.build_settings['ENABLE_BITCODE'] = 'NO'
      config.build_settings['VALID_ARCHS'] = '$(ARCHS_STANDARD_64_BIT)'
      config.build_settings['IPHONEOS_DEPLOYMENT_TARGET'] = '14.0'
      config.build_settings['BUILD_LIBRARY_FOR_DISTRIBUTION'] = 'YES'
    end
  end
end
```

## Tutorial

Visit this [tutorial](https://devdocs.mimik.com/tutorials/03-index) to learn more about the mimik client library and how to integrate it into your iOS project.

## mimik client and service libraries

Don't forget to checkout all mimik client and service libraries [available on Github](https://github.com/search?q=cocoapod-MIMIKEdgeClient)

Direct links:
 
 * [MIMIKEdgeClientCore](https://github.com/mimikgit/cocoapod-MIMIKEdgeClientCore)
 * [MIMIKEdgeClientEngine](https://github.com/mimikgit/cocoapod-MIMIKEdgeClientEngine)
 * [MIMIKEdgeClientUser](https://github.com/mimikgit/cocoapod-MIMIKEdgeClientUser)
 * [MIMIKEdgeClientAssessment](https://github.com/mimikgit/cocoapod-MIMIKEdgeClientAssessment)
 * [MIMIKEdgeClientNotification](https://github.com/mimikgit/cocoapod-MIMIKEdgeClientNotification)
 * [MIMIKEdgeClientTracker](https://github.com/mimikgit/cocoapod-MIMIKEdgeClientTracker)
 * [MIMIKEdgeClientContentCache](https://github.com/mimikgit/cocoapod-MIMIKEdgeClientContentCache)

## Author

mimik
```
https://github.com/mimikgit/cocoapod-MIMIKEdgeClientUser
```

## License

The aforementioned mimik client and service libraries are available under the MIT license. See the LICENSE file for more information.
