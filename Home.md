# Welcome to the MultiWindowAndroid wiki!
## Summary
This MultiWindowAndroid project is basing on Android KitKat 4.4, which support the APPs' window to drag, maximun, minimun, close, and resize, it looks pretty like the Windows OS.

![](http://img.my.csdn.net/uploads/201406/17/1403015500_1406.jpg)

![](http://img.my.csdn.net/uploads/201406/17/1403015499_8171.png)

Demo Vedio: http://v.youku.com/v_show/id_XNzI4ODg4NTM2.html

## Procedure
### For user
1. This patch only for KitKat 4.4, so please apply it in a clean branch.
In the root of AOSP:<br/>
$ git apply xxx.patch

2. Source and lunch, choose the "aosp_flo-userdebug" for Nexus 7 2013 WIFI:<br/>
$ source build/envsetup.sh<br/>
$ lunch

3. Build:<br/>
$ make -j8 otapackage

4. Flash your device

### For developer
You'd better git init in the root of AOSP, and git add the build/ frameworks/ packages/, To generate a patch:

1. Git diff a patch:<br/>
$ git diff INITIAL_COMMIT_ID --binary > xxx.patch 

