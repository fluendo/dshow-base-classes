DirectShow Base Classes
=======================

This project aims to build the DirectShow base classes on the latest Windows
versions for GStreamer gst-plugins-bad DirectShow plugins.

All Microsoft source code must be used and redistributed under the
corresponding EULA that you can find in *include* and *src* subfolders.

In particular, in section *2.a.i - Sample Code.*:
> You may modify, copy, and distribute the source and object code form of code
> marked as “sample.”

All content of *include* and *src* folders is directly copied (without
modification) from **Microsoft Windows SDK** version 7.1 DVD
(https://www.microsoft.com/en-us/download/details.aspx?id=8442),
*/Setup/WinSDKSamples* installer, *C:\Program Files (x86)\Microsoft
SDKs\Windows Kits\v7.1A\samples\multimedia\baseclasses*.

The project builds a static library called *strmbase* needed by GStreamer
gst-plugins-bad to build */sys/dshowdecwrapper*, */sys/dshowsrcwrapper* and
*/sys/dshowvideosink* plugins.

To build the *strmbase* library, just call:
```
meson builddir
ninja -C builddir
```

If you need to integrate this subproject with an old version of GStreamer
source code that would not provide it, you can use the patch files in
*gst-patch* subfolder. Just go to your GStreamer local git clone and run:
```
git apply /path/to/dshow-base-classes/gst-patch/*
```
before configuring meson.
