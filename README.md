# Embed a Unity project into an iOS native project

Great thanks to [jiulongw](https://github.com/jiulongw/swift-unity).
Almost all done in his project. I just fixed some bugs, improve post build logic and work around new versions of Unity and XCode

This demo supports Unity 2019.1.+ and XCode 10.2 (iOS 12.2, Swift 5)

## How to build demo:
1. Open Unity project switch target to iOS. Launch Demo scene and build project in any folder.
2. When the build is over you will see PostBuild editor window. Browse and select ios-demo-project file, click run post build proccess.
3. Launch iOS demo project select device or generic target (not simulator) and build the project.

## How to use in empty project

### XCode
1. Copy Unity folder with all [extra files](https://github.com/ese9/SwiftUnityPatching/tree/master/extras) in root of you XCode project.
2. Select your porject -> Info -> Configurations and select Unity configuration file (Debug and Release)
3. Update AppDelegate.swift and other files with logic you want (see sample code in [demo](https://github.com/ese9/SwiftUnityPatching/tree/master/ios-demo-project/DemoProject))

### Unity
1. Copy this [post build script](https://github.com/ese9/SwiftUnityPatching/blob/master/unity-demo-project/Assets/SwiftPatching/Editor/XcodePostBuild.cs) to your Unity project's Assets folder. Put anywhere you like but since this is an editor script, Unity requires it to be under a folder named Editor.
2. Build project and select XCode project for patching after that.

### Notes
- No need to patch it every time after unity build. Just chose the same folder for unity build and XCode project will automatically update
- XCode build can fail first time. Press `cmnd + shift + K` and run build again.
