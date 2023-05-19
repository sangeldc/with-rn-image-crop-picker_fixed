# with-rn-image-crop-picker_fixed

Expo config plugin for [react-native-image-crop-picker_fixed](https://github.com/sangeldc/with-rn-image-crop-picker_fixed).

## About

This plugin adds the required attributes to the specific files as mentioned in the [docs.](https://github.com/sangeldc/with-rn-image-crop-picker_fixed#step-3)

### iOS

InfoPlist:

- `NSPhotoLibraryUsageDescription`
- `NSCameraUsageDescription`
- `NSMicrophoneUsageDescription`

### Android

AndroidManifest: 
- `<uses-permission android:name="android.permission.CAMERA"/>`
- `<uses-permission android:name="android.permission.READ_MEDIA_IMAGES"/>`

Project build.gradle:

- `maven { url 'https://maven.google.com' }`
- `maven { url "https://www.jitpack.io" }`

App build.gradle `vectorDrawables.useSupportLibrary = true`

## Important note

Currently there is no full support for front-camera on android.

Requires Expo Dev Client in half-managed workflow.
Learn more about:

- Expo Managed Workflow in 2021: [part 1](https://blog.expo.io/expo-managed-workflow-in-2021-5b887bbf7dbb), [part 2](https://blog.expo.io/expo-managed-workflow-in-2021-d1c9b68aa10)
- [Expo dev-client docs](https://docs.expo.dev/clients/getting-started/)
- [Expo config plugin](https://docs.expo.io/guides/config-plugins)

## Usage

1. Install with Expo

```sh
$ expo install with-rn-image-crop-picker expo-build-properties
```

2. Check your app.json. It should look like this:

```json
 "plugins": [
      "with-rn-image-crop-picker_fixed",
      [
        "expo-build-properties",
	{
          "android": {
            "compileSdkVersion": 33,
            "targetSdkVersion": 33
	  }
	}
      ]
    ],
```

3. Rebuild your app

```sh
$ expo prebuild
$ expo run:ios --device
$ expo run:android --device
```

## Configuartion

You can configure the iOS messages by adding the following props to your app.json file:

- PhotoLibraryUsageDescription
- CameraUsageDescription
- MicrophoneUsageDescription

Example:

```json
"plugins": [
  [
		"with-rn-image-crop-picker",
		{
			"PhotoLibraryUsageDescription": "Allow app XYZ to access your photos",
			"CameraUsageDescription": "Allow app XYZ to access your camera",
			"MicrophoneUsageDescription": "Allow app XYZ to access your microphone"
		}
	]
]
```

## Contributing

Contributions are very welcome!

