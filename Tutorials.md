# Tutorials concerning Godot Engine

## Export on Android

### Prerequisites
* [Godot Engine](https://godotengine.org/download)
* [Android SDK](https://developer.android.com/studio)
* [Java JDK](https://www.oracle.com/technetwork/java/javase/downloads/index.html)

### Basic setup
* Project - Install android build template - Download
* Project - Export - Add - Android

### Advanced export (with android modules) setup
* First you have to setup a Basic export in order to have the **build** folder for android
* Then you have to import you module in the build folder of the project 
(More info [here](https://docs.godotengine.org/en/latest/tutorials/plugins/android/android_plugin.html))
* Create a [debug.keystore](https://coderwall.com/p/r09hoq/android-generate-release-debug-keystores)
* Configure your editor settings : Editor - Editor settings - Android  
You have to enter the path of Adb, Jarsigner, Debug Keystore and the Custom Build SDK Path.  
ADB is in your SDK folder (Example: ~/Android/sdk/platform-tools/)  
Jarsigner is in your JDK folder (Example: $JAVA_HOME/bin)
* Configure the project settings : Project - Project settings - Android - Insert in the module section the full path of your module.  
Example : The module in the **org.godotengine.godot** package named **TestModule** correspond to this following path : **org/godotengine/godot/TestModule**  
If you want to insert more than one module you can insert multiple path separed by a comma. Example : **org/godotengine/godot/TestModule,org/godotengine/godot/RunModule**
* Check the **Use Custom Build** option in the Export option
* You have to check the folowing permissions : **Read external storage / Write external storage / Manage Documents / Record Audio**
* Go into the resources tab and add in the **include field** the folowing string : data/*


### Export
To obtain an APK : Project - Export - Android - Export project  
To install directly on device : Plug a device with 
[USB debugging](https://developer.android.com/studio/debug/dev-options) enabled - 
Make sure that you authorize the computer to be connected with your device - 
Click on the android logo on the top right corner of the Godot Editor

### Problem faced

#### Application crashes on open
* Maybe you didn't import the module correctly. Make sure the path in the project settings is correct.
* If you install the application on a pretty old device. You have to change the GLES version from 3 to 2. Just click on the top right corner of the editor.

#### Could not install to device
* If the application is already installed in your device, try to uninstall it.
* Becareful with your files name. Some special characters aren't well supported in the manisfest.xml of Android. For example the file **[a].png** will cause problem when exported to android

#### Anyway you can run `adb logcat` to see the logcat on the terminal and try to debug your app
