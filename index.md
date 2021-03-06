title: Home

# AimDroid: Activity-Insulated Multi-level Automated Testing for Android Applications





<img class="img-responsive" style="margin:0 auto;max-width:600px;height:auto;" src="overview.png" alt="Overview"/>



## Artifact Evaluation Guide

We have provided all binaries for running AimDroid on an emulator.

* [Install AimDroid on Emulator](./install-AimDroid-on-an-emulator.html)

We suggest you to use AimDroid to test real commercial industrial-strength sealed apps with hundreds activities.
You can refer to the list of apps used during our evaluation.

* [Subject Apps](./apps-for-test.html)

We have another testing framework SATA.
SATA can run on Android 6 and 7 without root access to the phone.
We now working on implementing AimDroid on SATA.

* [SATA: Steering Automated Testing for Android Applications](http://gutianxiao.com/sata)

**Download this website (including every web page and artifact) from github for anonymous artifact evaluation.**

* <https://github.com/icsnju/AimDroid-ICSME-2017>
* You can view this website at your computer via any http server.
    * `cd AimDroid-ICSME-2017 && python2 -m SimpleHTTPServer` and then visit <http://localhost:8000>


## Source

AimDroid contains the following subprojects.

1. [AimDroid-controller](https://github.com/icsnju/AimDroid-controller)
2. [AimDroid-ape](https://github.com/icsnju/AimDroid-ape)
3. [AimDroid-monitor](https://github.com/icsnju/AimDroid-monitor)
4. MiniTrace: For collecting method/instruction coverage inside the VM
    * Runtime over [xposed-marshmallow](https://github.com/icsnju/minitrace-on-xposed-marshmallow)
    * Runtime over [dalvikvm](https://github.com/icsnju/minitrace-on-dalvikvm)
    * [Parser](https://github.com/icsnju/AimDroid-coverage-parser)

## AimDroid on Unrooted Device

* [How to enable AimDroid to run on unrooted devices?](unrooted-AimDroid.html)
