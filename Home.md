# Welcome to the MultiWindowAndroid wiki!
## Summary
This MultiWindowAndroid project is basing on Android KitKat 4.4, which support the APPs' window to drag, maximun, minimun, close, and resize, it looks pretty like the Windows OS.

![](http://img.my.csdn.net/uploads/201406/17/1403015500_1406.jpg)

![](http://img.my.csdn.net/uploads/201406/17/1403015499_8171.png)

Demo vedio: http://v.youku.com/v_show/id_XNzI4ODg4NTM2.html

## Procedure
### For user
1. Watch and check is there any error brfore apply the patch file:
<pre class="plaincode">$ git apply --stat /the/directory/of/xxx.patch</pre>
<pre class="plaincode">$ git apply --check /the/directory/of/xxx.patch</pre>
If there is no error, skip step 2.

2. This patch only for KitKat 4.4 (Tag: android-4.4_r1), so please apply it in a clean branch.
If there's any error in step 1, you cannot apply simply.
for example, you may got this information:
<pre class="plaincode">
error: patch failed: build/target/product/sdk.mk:62
error: build/target/product/sdk.mk: patch does not apply
error: patch failed: frameworks/base/core/java/android/app/ActivityThread.java:558
error: frameworks/base/core/java/android/app/ActivityThread.java: patch does not apply
</pre>
Then, you can reset the git repo build/ and /frameworks/base/ to android-4.4_r1
<pre class="plaincode">$ cd base/</pre>
<pre class="plaincode">$ git reset --hard android-4.4_r1</pre>
<pre class="plaincode">$ cd frameworks/base/</pre>
<pre class="plaincode">$ git reset --hard android-4.4_r1</pre>
finally, <code>git apply --check </code> again till there's no error.

3. In the root of AOSP, apply the patch file:
<pre class="plaincode">$ git apply xxx.patch</pre>

4. Source and lunch, choose the "aosp_flo-userdebug" for Nexus 7 2013 WIFI:
<pre class="plaincode">$ source build/envsetup.sh</pre>
<pre class="plaincode">$ lunch</pre>

5. Build:
<pre class="plaincode">$ make -j8 otapackage</pre>

6. Flash your device

### For developer
You'd better git init in the root of AOSP, and git add the build/ frameworks/ packages/, To generate a patch:

1. Git diff a patch:
<pre class="plaincode">$ git diff INITIAL_COMMIT_ID --binary > xxx.patch </pre>

