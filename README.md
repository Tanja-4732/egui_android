# egui demo app for mobile

FYI this is just an experiment, based on the work of others;  
I didn't make the vast majority of this code, but the section on [prerequisites](#prerequisites) may be very useful to you.

---

This is an example based on [agdk-egui example](https://github.com/rust-mobile/rust-android-examples), using `egui`, `winit` and `wgpu` to run [egui_demo_app](https://github.com/emilk/egui/tree/master/egui_demo_app).

To run this on desktop, just do `cargo run` like normal! For mobile, use `cargo android run` and `cargo apple run` respectively (or use `cargo android open` and `cargo apple open` to open in Android Studio and Xcode respectively).

## Development

### Desktop

Simply `cargo run`

### Android

Just run `cargo android init` to generate the Android project, then `cargo android run` to run it,
assuming you have the Android NDK and SDK installed (see below).

#### Prerequisites

The following guide is based on https://github.com/tauri-apps/wry/blob/dev/MOBILE.md, as seen on 2023-11-01 05:29:29.

1. Install the Android NDK and SDK
    ```zsh
    sudo pacman -S jdk-openjdk
    export $NDK_HOME=$HOME/Android/Sdk/ndk/25.0.8775105
    export $ANDROID_HOME=$HOME/Android/Sdk
    export $JAVA_HOME=/usr/lib/jvm/java-19-amazon-corretto
    ```
2. Set the Java version
    ```zsh
    sudo archlinux-java set java-19-amazon-corretto
    ```
3. Use Android Studio to install the following
    - Android Sdk Platform 33
    - Android SDK Platform-Tools
    - NDK (Side by side) 25.0.8775105
    - Android SDK Build-Tools 33.0
    - Android SDK Command-line Tools
    (hit the details button to see all version numbers)
4. Install the rust toolchain
    ```zsh
    rustup target add aarch64-linux-android armv7-linux-androideabi i686-linux-android x86_64-linux-android
    ```
5. Install cargo-mobile (2)
    ```zsh
    cargo install --git https://github.com/tauri-apps/cargo-mobile2
    ```

### iOS

Legend has it you can run `cargo apple run` and it may work.  
But that requires macOS, so what gives.
