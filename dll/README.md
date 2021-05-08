## Building Instructions

For building this you'll want to follow Google's [instructions](https://github.com/google/angle/blob/master/doc/DevSetup.md) on setting up the environment. You'll need to do this on Windows 10, and have all the prerequisites installed, like VS Community and the Windows 10 SDK.

Use the following to build once it's all set up:

```bash
gn gen out/x64 --args='is_debug=false dcheck_always_on=false target_cpu=\"x64\"'
gn gen out/x86 --args='is_debug=false dcheck_always_on=false target_cpu=\"x86\"'

ninja -C out/x64 libEGL libGLESv2
ninja -C out/x86 libEGL libGLESv2
```

Copy the `out/*/libGLESv2.dll` and `out/*/libEGL.dll` to where you need them and build Taisei with them (i.e: with `-Dangle_libgles=/path/to/libGLESv2.dll` and `-Dangle_libegl=/path/to/libEGL.dll`).
