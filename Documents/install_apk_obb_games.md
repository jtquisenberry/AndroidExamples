# Create a new AVD

* Pixel 4
* API Level 30
* Google Play Intel x86 Atom System Image

Start the AVD.


# Install the APK

Drag and drop the APK from the host PC to the running AVD.

# Root the AVD

Follow the instructions "Root AVD Android Studio".

# Copy the OBB

Start the shell within the AVD using ADB on the host PC.

```
> adb shell
```

Get root privileges. 

```
$ su
generic_x86_arm:/ #
```

Navigate to obb/ directory

```
# cd /sdcard/Android/obb
```

Create the directory for the OBB file. Give the directory the same name as the name of the package.

```
# mkdir com.animocabrands.google.HeManTappersUniverse
```

Apply permissions to the directory

```
# cd com.animocabrands.google.HeManTappersUniverse
# chmod -R 777 .
```

Exit the ADB shell.

```
# exit
$ exit
>
```

Copy the OBB file from the host PC to the AVD.

```
> adb Tappers_of_Grayskull\com.animocabrands.google.HeManTappersUniverse.obb /sdcard/Android/obb/com.animocabrands.google.HeManTappersUniverse/
```

# Restart the AVD

# Run the Game