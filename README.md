# Godot Meta Toolkit

The toolkit exposes Meta SDKs (e.g Platform SDK), as well as Meta utilities for XR development with the Godot Engine.

> [!WARNING]
>
> Use of the toolkit requires **Godot 4.3** or higher.

## Build instructions

After cloning the project, run the following command in the project root directory to initialize the submodules:
```
git submodule update --init --recursive
```

Then download the [Oculus Platform SDK](https://developer.oculus.com/downloads/package/oculus-platform-sdk/) and extract
it into `thirdparty/ovr_platform_sdk`, such that `thirdparty/ovr_platform_sdk/Include/OVR_Platform.h` exists.

We've tested with v71 of the Platform SDK.

### Build the toolkit

#### Linux / MacOS
Run the following command from the root directory to build the toolkit artifacts:
```
./gradlew buildToolkit
```

#### Windows
Run the following command from the root directory to build the toolkit artifacts:
```
gradlew.bat buildToolkit
```

## Using the Platform SDK

See [Getting Started with the Meta Platform SDK](https://godot-sdk-integrations.github.io/godot-meta-toolkit/manual/platform_sdk/getting_started.html) in the official docs.

## Documentation

This README is intentionally kept short.

See the [official documentation](https://godot-sdk-integrations.github.io/godot-meta-toolkit/) for more information.

## Maintenance and Sponsorship

This project is maintained by [W4 Games](https://www.w4games.com/) with sponsorship from [Meta](https://www.meta.com/).
