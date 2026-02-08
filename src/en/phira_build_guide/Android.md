# Android

## Build

::: warning
This build **does not include score upload** (similar to the Windows build).
:::

1. This guide uses **GitHub Actions** to build Android Phira; local build steps are TBD.
2. **Fork** the official Phira repo, create `.github/workflows/` and add a `.yml` file (any name).
3. Put the workflow content below into that file, commit, go to Actions → "Build Android Phira", **trigger the workflow** (choose branch if needed), wait ~5 minutes, then **download the artifact** and extract it.

::: tip
For armeabi-v7a, **replace** all "arm64-v8a" with "armeabi-v7a" and "aarch64-linux-android" with "armv7-linux-androideabi" (untested).
:::

(The YAML workflow is the same as in the source: checkout, install deps, download static-lib, set up Android SDK/NDK, install Rust target aarch64-linux-android, run `cargo ndk -t arm64-v8a --platform 35 build --release`, upload artifact with libphira.so.)

## Replacing the library in the APK

> There is no packaging tool provided; you must manually replace `libphira.so` in an APK.

> **If you install and run as-is, you may see an error about quad_native.QuadNative.preprocessInput not found.**

### Method 1

1. Push `libphira.so` to your Android device (any path you know).
2. Download the APK for your architecture from the official Phira release; open it with MT Manager (or similar).
3. **Replace** `lib/arm64-v8a/libphira.so` (or armeabi-v7a) with your built `libphira.so`.
4. Open `classes.dex` with Dex Editor++, go to `org.flos.phira` and find the **QuadSurface** class.
5. Find the line that calls `preprocessInput` (e.g. around line 153) and remove or comment it.
6. Save, re-sign the APK as MT Manager instructs.
7. Optionally do an "APK coexistence" build if you need multiple installs.

### Method 2

#### Add this in `phira/src/lib.rs`:

```Rust
#[cfg(target_os = "android")]
#[no_mangle]
pub unsafe extern "C" fn Java_quad_1native_QuadNative_preprocessInput(
    _: *mut std::ffi::c_void,
    _: *const std::ffi::c_void,
    #[allow(dead_code)] motionEvent: ndk_sys::AInputEvent,
    #[allow(dead_code)] f: ndk_sys::jfloat,
    #[allow(dead_code)] f2: ndk_sys::jfloat,
    #[allow(dead_code)] z: ndk_sys::jboolean,
    #[allow(dead_code)] z2: ndk_sys::jboolean,
) {
    
}
```

## Credits

- Thanks to [qaqFei for testing](https://github.com/qaqFei/phira/tree/main).
