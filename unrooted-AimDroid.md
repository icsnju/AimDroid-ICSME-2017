title: AimDroid on Unrooted Devices


# AimDroid on Unrooted Devices


The current implementation of AimDroid requires to root the device to install the Xposed framework.
Currently, we leverage the Xposed framework to support the following operations.

1. To block/unblock the start of an activity and record the parameter intent.
2. Start an activity by directly call the API `startActivity` and its variants.


Actually, we have found that the Android framework has already provided necessary APIs to support AimDroid.
These APIs are used by Monkey to support the option `-p`, which is mainly used to block inter-app activity transitions.

1. To block/unlock activity start, we can implement a custom `IActivityController`. Check the method `activityStarting`.

        /**
         * The system is trying to start an activity.  Return true to allow
         * it to be started as normal, or false to cancel/reject this activity.
         */
        boolean activityStarting(in Intent intent, String pkg);

2. To start an [**exported**](https://developer.android.com/guide/topics/manifest/activity-element.html#exported) activity, we can use `IActivityManager`.

You can checkout the source code of [Monkey](https://github.com/android/platform_development/tree/master/cmds/monkey) to learn how to use these APIs.

Related hidden APIs:

1. [IActivityManager](https://android.googlesource.com/platform/frameworks/base/+/master/core/java/android/app/IActivityManager.java)
2. [IActivityController](https://android.googlesource.com/platform/frameworks/base.git/+/master/core/java/android/app/IActivityController.aidl)

Another technique challenge is to build and run AimDroid on a unrooted device. This might not be a problem since Android 6.0.
We are now working on improving SATA, a practical framework for black-box model-based testing for Android app.
Try [SATA](https://github.com/tianxiaogu/tianxiaogu.github.io/blob/master/sata/ape-bin.zip) on an unrooted device.
