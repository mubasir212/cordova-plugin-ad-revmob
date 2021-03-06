Cordova RevMob plugin
====================
# Overview #
Show revmob banner, interstitial, video, rewarded video, popup, link ad.

[android, ios] [cordova cli] [xdk] [cocoon] [phonegap build service]

Requires revmob account https://www.revmobmobileadnetwork.com

revmob-android-sdk-9.0.1 (2015/05/28)<br>
revmob-ios-sdk-9.0.1 (2015/05/28)

This is open source cordova plugin.

You can see Cordova Plugins in one page: http://cranberrygame.github.io?referrer=github

# Change log #
```c
1.0.63
	Updated sdk version to 9.0.1
1.0.64
	Fixed black screen issue
	
To-Do:

	supports ios banner
```
# Install plugin #

## Cordova cli ##
https://cordova.apache.org/docs/en/edge/guide_cli_index.md.html#The%20Command-Line%20Interface - npm install -g cordova@6.0.0
```c
cordova plugin add cordova-plugin-ad-revmob
(when build error, use github url: cordova plugin add cordova plugin add https://github.com/cranberrygame/cordova-plugin-ad-revmob)
```

## Xdk ##
https://software.intel.com/en-us/intel-xdk - Download XDK - XDK PORJECTS - [specific project] - CORDOVA HYBRID MOBILE APP SETTINGS - Plugin Management - Add Plugins to this Project - Third Party Plugins -
```c
Plugin Source: Cordova plugin registry
Plugin ID: cordova-plugin-ad-revmob
```

## Cocoon ##
https://cocoon.io - Create project - [specific project] - Setting - Plugins - Custom - Git Url: https://github.com/cranberrygame/cordova-plugin-ad-revmob.git - INSTALL - Save<br>

## Phonegap build service (config.xml) ##
https://build.phonegap.com/ - Apps - [specific project] - Update code - Zip file including config.xml
```c
<gap:plugin name="cordova-plugin-ad-revmob" source="npm" />
```

## Construct2 ##
Download construct2 plugin<br>
https://dl.dropboxusercontent.com/u/186681453/pluginsforcordova/index.html<br>
How to install c2 native plugins in xdk, cocoon and cordova cli<br>
https://plus.google.com/102658703990850475314/posts/XS5jjEApJYV

# Server setting #
```c
```

<img src="https://raw.githubusercontent.com/cranberrygame/cordova-plugin-ad-revmob/master/doc/RewardedVideo1.png"><br>
<img src="https://raw.githubusercontent.com/cranberrygame/cordova-plugin-ad-revmob/master/doc/RewardedVideo2.png"><br>
<img src="https://raw.githubusercontent.com/cranberrygame/cordova-plugin-ad-revmob/master/doc/RewardedVideo3.png">

test mode setting:<br>
https://www.revmobmobileadnetwork.com - Monetization - [specific app] - Edit Media - Testing Mode: select one among Off, With Ads and Without Ads 

Full screen ad video option: https://www.revmobmobileadnetwork.com - Monetization - [specific app] - Ad Units - Fullscreen - Edit - check Accepts Video or not

# API #
```javascript
var mediaId = "REPLACE_THIS_WITH_YOUR_MEDIA_ID";
var isOverlap = true; //true: overlap, false: split
/*
var mediaId;
var isOverlap = true; //true: overlap, false: split
//android
if (navigator.userAgent.match(/Android/i)) {
	mediaId = "REPLACE_THIS_WITH_YOUR_ANDROID_MEDIA_ID";
}
//ios
else if (navigator.userAgent.match(/iPhone/i) || navigator.userAgent.match(/iPad/i)) {
	mediaId = "REPLACE_THIS_WITH_YOUR_IOS_MEDIA_ID";
}
*/

document.addEventListener("deviceready", function(){
	//if no license key, 2% ad traffic share for dev support.
	//you can get paid license key: https://cranberrygame.github.io/request_cordova_ad_plugin_paid_license_key
	//window.revmob.setLicenseKey("yourEmailId@yourEmaildDamin.com", "yourLicenseKey");
	
	window.revmob.setUp(mediaId, isOverlap);

	//
	window.revmob.onBannerAdPreloaded = function() {
		alert('onBannerAdPreloaded');
	};
	window.revmob.onBannerAdLoaded = function() {
		alert('onBannerAdLoaded');
	};
	window.revmob.onBannerAdShown = function() {
		alert('onBannerAdShown');
	};
	window.revmob.onBannerAdHidden = function() {
		alert('onBannerAdHidden');
	};	
	//
	window.revmob.onInterstitialAdPreloaded = function() {
		alert('onInterstitialAdPreloaded');
	};
	window.revmob.onInterstitialAdLoaded = function() {
		alert('onInterstitialAdLoaded');
	};
	window.revmob.onInterstitialAdShown = function() {
		alert('onInterstitialAdShown');
	};
	window.revmob.onInterstitialAdHidden = function() {
		alert('onInterstitialAdHidden');
	};
	//
	window.revmob.onVideoAdPreloaded = function() {
		alert('onVideoAdPreloaded');
	};
	window.revmob.onVideoAdLoaded = function() {
		alert('onVideoAdLoaded');
	};
	window.revmob.onVideoAdShown = function() {
		alert('onVideoAdShown');
	};
	window.revmob.onVideoAdHidden = function() {
		alert('onVideoAdHidden');
	};
	//
	window.revmob.onRewardedVideoAdPreloaded = function() {
		alert('onRewardedVideoAdPreloaded');
	};
	window.revmob.onRewardedVideoAdLoaded = function() {
		alert('onRewardedVideoAdLoaded');
	};
	window.revmob.onRewardedVideoAdShown = function() {
		alert('onRewardedVideoAdShown');
	};
	window.revmob.onRewardedVideoAdHidden = function() {
		alert('onRewardedVideoAdHidden');
	};
	window.revmob.onRewardedVideoAdCompleted = function() {
		alert('onRewardedVideoAdCompleted');
	};	
	//
	window.revmob.onPopupAdPreloaded = function() {
		alert('onPopupAdPreloaded');
	};
	window.revmob.onPopupAdLoaded = function() {
		alert('onPopupAdLoaded');
	};
	window.revmob.onPopupAdShown = function() {
		alert('onPopupAdShown');
	};
	window.revmob.onPopupAdHidden = function() {//not implemented yet
		alert('onPopupAdHidden');
	};
	//
	window.revmob.onLinkAdPreloaded = function() {
		alert('onLinkAdPreloaded');
	};
	window.revmob.onLinkAdLoaded = function() {
		alert('onLinkAdLoaded');
	};
	window.revmob.onLinkAdShown = function() {
		alert('onLinkAdShown');
	};
	window.revmob.onLinkAdHidden = function() {//not implemented yet
		alert('onLinkAdHidden');
	};
}, false);

window.revmob.preloadBannerAd();//option, download ad previously for fast show
/*
//position: 'top-left', 'top-center', 'top-right', 'left', 'center', 'right', 'bottom-left', 'bottom-center', 'bottom-right'
position: 'bottom-center' //only 'bottom-center' is supported
*/
//window.revmob.showBannerAd('top-center');
window.revmob.showBannerAd('bottom-center');
window.revmob.reloadBannerAd();
window.revmob.hideBannerAd();

window.revmob.preloadInterstitialAd();//option, download ad previously for fast show
window.revmob.showInterstitialAd();

window.revmob.preloadVideoAd();//option, download ad previously for fast show
window.revmob.showVideoAd();

window.revmob.preloadRewardedVideoAd();//option, download ad previously for fast show
window.revmob.showRewardedVideoAd();

window.revmob.preloadPopupAd();//option, download ad previously for fast show
window.revmob.showPopupAd();

window.revmob.preloadLinkAd();//option, download ad previously for fast show
window.revmob.showLinkAd();

alert(window.revmob.loadedBannerAd());//boolean: true or false
alert(window.revmob.loadedInterstitialAd());//boolean: true or false
alert(window.revmob.loadedVideoAd());//boolean: true or false
alert(window.revmob.loadedRewardedVideoAd());//boolean: true or false
alert(window.revmob.loadedPopupAd());//boolean: true or false
alert(window.revmob.loadedLinkAd());//boolean: true or false

alert(window.revmob.isShowingBannerAd());//boolean: true or false
alert(window.revmob.isShowingInterstitialAd());//boolean: true or false
alert(window.revmob.isShowingVideoAd());//boolean: true or false
alert(window.revmob.isShowingRewardedVideoAd());//boolean: true or false
alert(window.revmob.isShowingPopupAd());//boolean: true or false
alert(window.revmob.isShowingLinkAd());//boolean: true or false
```
# Examples #
<a href="https://github.com/cranberrygame/cordova-plugin-ad-revmob/blob/master/example/basic/index.html">example/basic/index.html</a><br>
<a href="https://github.com/cranberrygame/cordova-plugin-ad-revmob/blob/master/example/advanced/index.html">example/advanced/index.html</a>

# Test #

[![](http://img.youtube.com/vi/fThTXn88dNw/0.jpg)](https://www.youtube.com/watch?v=fThTXn88dNw&feature=youtu.be "Youtube")

You can also run following test apk.
https://dl.dropboxusercontent.com/u/186681453/pluginsforcordova/revmob/apk.html

# Useful links #

Cordova Plugins<br>
http://cranberrygame.github.io?referrer=github

# Credits #

https://github.com/RevMob/cordova-plugin

https://github.com/blakgeek/cordova-plugin-revmob
