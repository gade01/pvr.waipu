[![Build Status](https://travis-ci.org/flubshi/pvr.waipu.svg?branch=Matrix)](https://travis-ci.org/flubshi/pvr.waipu) [![Build status](https://ci.appveyor.com/api/projects/status/mak70bfs0bj78y53/branch/Matrix?svg=true)](https://ci.appveyor.com/project/flubshi/pvr-waipu/branch/Matrix) [![Build Status](https://jenkins.kodi.tv/buildStatus/icon?job=flubshi%2Fpvr.waipu%2FMatrix)](https://jenkins.kodi.tv/job/flubshi/job/pvr.waipu/job/Matrix/)

# waipu PVR
waipu PVR client addon for [Kodi](http://kodi.tv)

## Installation

Starting with Kodi 19 - Matrix, pvr.waipu will become an official Kodi plugin and should be shipped with your installation. Current test distributions, like [Milhouse LibreELEC Nightlies](https://forum.kodi.tv/showthread.php?tid=343068) or [gmc OSMC Nightlies](https://discourse.osmc.tv/t/kodi-19-matrix-nightly-builds-for-raspberry-pi/79407) already ship pvr.waipu.

pvr.waipu also supports the stable version Kodi 18 - Leia. To use it, you need to compile it yourself, or download and install a precompiled version:

|Platform|Kodi 18|Kodi 19|
|---|---|---|
|Windows (x64)|[Download](https://jenkins.kodi.tv/job/flubshi/job/pvr.waipu/job/Leia/lastSuccessfulBuild/artifact/cmake/addons/build/zips/pvr.waipu+windows-x86_64/)|[Download](https://jenkins.kodi.tv/job/flubshi/job/pvr.waipu/job/Matrix/lastSuccessfulBuild/artifact/cmake/addons/build/zips/pvr.waipu+windows-x86_64/)|
|Windows (i686)|[Download](https://jenkins.kodi.tv/job/flubshi/job/pvr.waipu/job/Leia/lastSuccessfulBuild/artifact/cmake/addons/build/zips/pvr.waipu+windows-i686)|[Download](https://jenkins.kodi.tv/job/flubshi/job/pvr.waipu/job/Matrix/lastSuccessfulBuild/artifact/cmake/addons/build/zips/pvr.waipu+windows-i686)|
|OSX (x64)|[Download](https://jenkins.kodi.tv/job/flubshi/job/pvr.waipu/job/Leia/lastSuccessfulBuild/artifact/cmake/addons/build/zips/pvr.waipu+osx-x86_64)|[Download](https://jenkins.kodi.tv/job/flubshi/job/pvr.waipu/job/Matrix/lastSuccessfulBuild/artifact/cmake/addons/build/zips/pvr.waipu+osx-x86_64)|
|Android (aarch64)|[Download](https://jenkins.kodi.tv/job/flubshi/job/pvr.waipu/job/Leia/lastSuccessfulBuild/artifact/cmake/addons/build/zips/pvr.waipu+android-aarch64)|[Download](https://jenkins.kodi.tv/job/flubshi/job/pvr.waipu/job/Matrix/lastSuccessfulBuild/artifact/cmake/addons/build/zips/pvr.waipu+android-aarch64)|
|Android (ARMv7)|[Download](https://jenkins.kodi.tv/job/flubshi/job/pvr.waipu/job/Leia/lastSuccessfulBuild/artifact/cmake/addons/build/zips/pvr.waipu+android-armv7)|[Download](https://jenkins.kodi.tv/job/flubshi/job/pvr.waipu/job/Matrix/lastSuccessfulBuild/artifact/cmake/addons/build/zips/pvr.waipu+android-armv7)|
|iOS (aarch64)|[Download](https://jenkins.kodi.tv/job/flubshi/job/pvr.waipu/job/Leia/lastSuccessfulBuild/artifact/cmake/addons/build/zips/pvr.waipu+ios-aarch64)|[Download](https://jenkins.kodi.tv/job/flubshi/job/pvr.waipu/job/Matrix/lastSuccessfulBuild/artifact/cmake/addons/build/zips/pvr.waipu+ios-aarch64)|
|iOS (ARMv7)|[Download](https://jenkins.kodi.tv/job/flubshi/job/pvr.waipu/job/Leia/lastSuccessfulBuild/artifact/cmake/addons/build/zips/pvr.waipu+ios-armv7)|[Download](https://jenkins.kodi.tv/job/flubshi/job/pvr.waipu/job/Matrix/lastSuccessfulBuild/artifact/cmake/addons/build/zips/pvr.waipu+ios-armv7)|

## Disclaimer

This is an *unofficial* plugin. It is provided by volunteers and not related to Exaring AG or waipu.tv.
For any support regarding this plugin, please create a github issue.


## Build instructions

### Linux

```bash
git clone --branch Leia https://github.com/xbmc/xbmc.git
mkdir -p xbmc/cmake/addons/addons/pvr.waipu/
echo "pvr.waipu https://github.com/flubshi/pvr.waipu Leia" > xbmc/cmake/addons/addons/pvr.waipu/pvr.waipu.txt
echo "all" > xbmc/cmake/addons/addons/pvr.waipu/platforms.txt

git clone --branch Leia-Backported https://github.com/flubshi/pvr.waipu.git
mkdir -p pvr.waipu/build && cd pvr.waipu/build

cmake -DADDONS_TO_BUILD=pvr.waipu -DADDON_SRC_PREFIX=../.. -DCMAKE_BUILD_TYPE=Debug -DCMAKE_INSTALL_PREFIX=../../xbmc/addons -DPACKAGE_ZIP=1 ../../xbmc/cmake/addons
make
```


## Useful links

* [Kodi's PVR user support](http://forum.kodi.tv/forumdisplay.php?fid=167)
* [Kodi's PVR development support](http://forum.kodi.tv/forumdisplay.php?fid=136)
