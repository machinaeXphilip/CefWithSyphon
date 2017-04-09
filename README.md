CefWithSyphon
=============

This is an application for Mac OS X that allows you to share the contents of a web browser
(based on Chrome) using Syphon. It implements most of the things you'd expect except pop
up windows (at the moment). Complicated html pages do not run as fast as a real Chrome browser
but Flash and WebGL seems to run smoothly.

About this fork
---------------

This fork updates “vibber/CefWithSyphon” with CEF release 3.2987.1600.g9ea5b3b (April 06, 2017).
Unlike the original, this version adds support for ECMAScript 6 and WebRTC.

This fork was created by cloning vibber’s repository and replacing all the files with the following
updated CEF source:

http://opensource.spotify.com/cefbuilds/cef_binary_3.2987.1600.g9ea5b3b_macosx64.tar.bz2

I then manually ported over changes from vibber’s original into this new version of CEF. A few of
the files had moved, but I tried my best to find the correct locations for the modifications based on
the surrounding code. I also did my best to update the CMAKE files. Everything seems to work, but
I am a newbie at Mac OS development, CMAKE, CEF or Syphon so I cannot guarantee correctness.

The "Syphon.framework" is also the latest as of April 08, 2017. I compiled it with XCode
from the sources at this location:

https://github.com/syphon/syphon-framework
http://syphon.v002.info/

This updated build of CefWithSyphon was created to support my [dome projection experiments](http://marciot.com/dome-experiments).

Building with CMake and XCode
-----------------------------

1. Unpack the tar archives "cef_binary_release.tgz" and "cef_binary_debug.tgz"
2. Download and install the MacOS version of CMake from “cmake.org”
3. Run the CMake application.
4. Set “Where is the source code:” to the top-level of this repository
5. Set “Where to build the binaries:” to “XCodeBuild” in the top-level of this repository
6. Click “Configure” (select XCode when asked)
7. Click "Generate"
8. Open the project "XCodeProject/cef.xcodeproj" in XCode
9. Build
10. The CefWithSyphon will be compiled to "XCodeBuild/tests/cefclient/Debug/cefclient.app"

This build process has been tested with XCode 8.2 and CMAKE 3.8.0rc4

About Syphon
------------

Syphon is a brilliant (Mac OS X only) way to share frames between applications with almost no performance penalty. It is used a lot in live visual performance and creative coding circles.

Learn about Syphon: http://syphon.v002.info

About CEF (Chromium Embedded Framework)
---------------------------------------

As the name implies this application uses CEF3. This is a wrapper around Chromium which makes it possible to use the Chrome technology embedded in regular desktop applications for Mac OSX, Windows and Linux. Chromium is the open source project behind Google Chrome.

https://bitbucket.org/chromiumembedded/cef
