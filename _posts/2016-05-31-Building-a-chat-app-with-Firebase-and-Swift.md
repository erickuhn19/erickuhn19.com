---
layout: post
title: Building a chat app with Firebase and Swift
category: blog
date: '2016-05-31'
---

So in my [last post on Google I/O](http://erickuhn19.com/google-io-2016-thoughts/) I mentioned I was going to explore Firebase and I’ve been doing just that. The Firebase team has great documentation on their site as well as some helpful tutorials. I completed the iOS building a messaging app with Swift. You can find the link [here.](https://codelabs.developers.google.com/codelabs/firebase-ios-swift)

It was very cool to see the power behind the SDK and how Firebase can augment so many backend things you would have to build into your API. I followed along but getting to understand all the functions is really where you can unlock Firebase’s true potential. I plan on doing this over the next few weeks.

In the tutorial you learn how to set up the following:

*   Sync data using the Firebase Realtime Database.
*   Manage Identity and Sign In with Firebase Authentication
*   Store and access files using Firebase Storage.
*   Configure an application with Firebase Remote Config.
*   Track application usage flows with Firebase Analytics.
*   Display ads with AdMob.

However, there were a few issues with the documentation. Nothing a little stackoverflow/github googling couldn’t fix. Here are the fixes:

Section 8: [stackoverflow link](http://stackoverflow.com/questions/37383187/error-in-firebase-ios-codelab-chat-app-tutorial)

Need to add to the Constants.Swift file

`swift static let imageUrl = "imageUrl"`

All looked good after that and then I caught this error when I complied.

> FriendlyChatSwift[7097:353609] _** Assertion failure in -[UITableView _endCellAnimationsWithContext:], /BuildRoot/Library/Caches/com.apple.xbs/Sources/UIKit_Sim/UIKit-3512.60.7/UITableView.m:1716 2016-05-28 16:38:42.950 FriendlyChatSwift[7097:353609] **_ Terminating app due to uncaught exception 'NSInternalInconsistencyException', reason: 'Invalid update: invalid number of rows in section 0\. The number of rows contained in an existing section after the update (1) must be equal to the number of rows contained in that section before the update (27), plus or minus the number of rows inserted or deleted from that section (1 inserted, 0 deleted) and plus or minus the number of rows moved into or out of that section (0 moved in, 0 moved out).'

Here is the discussion on the [Firebase’s github page](https://github.com/firebase/friendlychat/issues/25) on the issue. The answer that ended up working for me came from this source on [stackoverflow.](http://stackoverflow.com/questions/37400316/image-upload-crash-in-firebase-codelabs-friendlychat-tutorial)

I also found an error in step 10, use this in the viewDidLoad:

`swift self.remoteConfig = FIRRemoteConfig.remoteConfig()`
