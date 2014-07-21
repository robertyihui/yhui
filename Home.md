# Welcome to the MultiWindowAndroid wiki!
## Summary
This MultiWindowAndroid project is basing on Android KitKat 4.4, which support the APPs' window to drag, maximun, minimun, close, and resize, it looks pretty like the Windows OS.

![](http://img.my.csdn.net/uploads/201406/17/1403015500_1406.jpg)

![](http://img.my.csdn.net/uploads/201406/17/1403015499_8171.png)

Demo vedio: http://v.youku.com/v_show/id_XNzI4ODg4NTM2.html

## Procedure
### For user
0.1. This patch only for KitKat 4.4 (Tag: android-4.4_r1), so please apply it in a clean branch.<br/>
<pre class="plaincode">$ git reset --hard android-4.4_r1</pre>

0.2. Watch and check is there any error brfore apply the patch file 
<pre class="plaincode">$ git apply --stat /the/directory/xxx.patch</pre>
<pre class="plaincode">$ git apply --check /the/directory/of/xxx.patch</pre>

1. In the root of AOSP, apply the patch file<br/>
<pre class="plaincode">$ git apply xxx.patch</pre>

2. Source and lunch, choose the "aosp_flo-userdebug" for Nexus 7 2013 WIFI:<br/>
<pre class="plaincode">$ source build/envsetup.sh<br/>
<pre class="plaincode">$ lunch</pre>

3. Build:<br/>
<pre class="plaincode">$ make -j8 otapackage</pre>

4. Flash your device

### For developer
You'd better git init in the root of AOSP, and git add the build/ frameworks/ packages/, To generate a patch:

1. Git diff a patch:<br/>
<pre class="plaincode">$ git diff INITIAL_COMMIT_ID --binary > xxx.patch </pre>

