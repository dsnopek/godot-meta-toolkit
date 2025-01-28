# GDExtension API

This directory contains the API JSON for
[**Godot Engine**](https://github.com/godotengine/godot)'s *GDExtensions* API.

## Current API version
- [commit 46dc277917a93cbf601bbcf0d27d00f6feeec0d5](https://github.com/godotengine/godot/commit/46dc277917a93cbf601bbcf0d27d00f6feeec0d5)

## Updating API

The API JSON is synced with the latest version of Godot used when developing the plugin. Here is the
update procedure:

- Compile [Godot Engine](https://github.com/godotengine/godot) at the specific
  version/commit which you are using.
  * Or if you use an official release, download that version of the Godot editor.
- Use the compiled or downloaded executable to generate the `extension_api.json` file with:

```
godot --dump-extension-api
```
- Copy the generated `extension_api.json` file into this directory
