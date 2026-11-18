# abcore

abcore is a Java-based Android app for running a personal Bitcoin Core node on an Android device, including always-on set-top boxes and home appliances. It fetches an Android-compatible daemon built with the NDK, so you can use a personal node with a wallet that supports connecting to one.

This project is based on [greenaddress/abcore](https://github.com/greenaddress/abcore). The upstream app is proof-of-concept/alpha software; do not rely on it as a wallet.

## Features

- Fetch Android-compatible Bitcoin Core daemon binaries during initial configuration.
- Run a personal Bitcoin node on Android 5.0 Lollipop (API 21) or later.
- Support x86, x86_64, armhf, and arm64 Android devices; MIPS is not supported.
- Connect to the Bitcoin network without advertising, in-app purchases, or phone-home telemetry.

## Installation

abcore is an Android application, not a desktop Java program. Install an APK with Android SDK Platform Tools; `java -jar` is not applicable.

You need a compatible Android device with USB debugging enabled and an APK built for this project. With the device connected, run:

```sh
adb devices
adb install /path/to/abcore.apk
```

Replace `/path/to/abcore.apk` with the actual APK path and authorize the debugging connection on the device if prompted.

The donor documentation does not specify a reproducible source-build command. Its [historical releases](https://github.com/greenaddress/abcore/releases) are upstream artifacts, not releases of this standalone project.

## Usage

For example, install abcore on an always-on Android device connected to your home network:

1. Open abcore from the Android launcher.
2. Complete the initial configuration. The app connects to GitHub to fetch the required daemon binaries.
3. Let the node synchronize over a stable connection.
4. Use the node with a wallet that supports connecting to a specific personal node, following that wallet's connection instructions.

Plan for substantial memory, storage, and network use. Upstream reported testing with 2 GB of RAM and 256 GB of storage for an unpruned node; these are historical test figures, not current sizing guarantees. A 3G or 4G connection is not recommended, and network charges may apply.

Use abcore as a personal blockchain node rather than as a wallet. Contributors are not responsible for costs or damage caused by running the app, including data charges.

## License

abcore is licensed under the MIT license and is based on [greenaddress/abcore](https://github.com/greenaddress/abcore). Preserve the upstream copyright and permission notices when redistributing the software or substantial portions of it. See [COPYING](COPYING) for the license text.
