CameraPermissionsTest
=====================

If the user has denied an application access to the camera, the status returned by ```authorizationStatusForMediaType:``` is ```AVAuthorizationStatusDenied```. If you redirect the user to your app's settings in Settings.app and they then grant access to the camera, when they return to the app, ```authorizationStatusForMediaType:``` still returns ```AVAuthorizationStatusDenied```.

If you relaunch the app, ```authorizationStatusForMediaType:``` correctly returns ```AVAuthorizationStatusAuthorized```.

I can't figure out how to detect the user has granted access via Settings.app.


Resolution
==========

I was being a doofus.

When you change the setting in Settings.app, your app is killed so the authorization status is correct on next launch. I was testing in the simulator so the debugger was keeping the app alive.
