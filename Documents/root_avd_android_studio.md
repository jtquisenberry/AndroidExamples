

# Instructions

1. Clone the rootAVD repository. Open a terminal or command prompt and run the following command to download the script:

The GitHub repository was archived in 2023. It has been moved to GitLab.

``` sh
git clone https://gitlab.com/newbit/rootAVD.git
cd rootAVD
```

GitHub option.

``` sh
git clone https://github.com/newbit1/rootAVD.git
cd rootAVD
```


2. Launch your AVD. Start the emulator from the Android Studio Device Manager.
1. Perform a cold boot. This is a critical step to ensure your rooting changes are saved and not lost when the emulator is restarted. In the Device Manager, click the drop-down arrow next to your AVD and select Cold Boot Now. Alternatively, launch it from the command line with the -no-snapshot-load flag.
1. List your AVDs. Run the rootAVD script with the ListAllAVDs command to see the available emulator images and their paths.

    On macOS/Linux: `./rootAVD.sh ListAllAVDs`
    On Windows: `rootAVD.bat ListAllAVDs`

1. Patch the AVD's ramdisk.img. From the output of the previous step, find the command that corresponds to your AVD and includes the path to the ramdisk.img. Copy and paste that command into your terminal and execute it.

    The script will detect the necessary files, install Magisk, and automatically shut down the AVD once complete.

    This procedure affects all AVDs built from the specified system image. In this example, devices built with the Android 11.0, API level 30 image.

``` sh
rootAVD.bat system-images\android-30\google_apis_playstore\x86\ramdisk.img
```


6. Complete the Magisk setup. After the script finishes, perform another cold boot of your AVD. When it restarts, you will find the Magisk app installed. Open it and follow any prompts for "additional setup" and a final reboot.
1. Verify root access. To confirm that the process was successful, follow these steps:

    * Open a terminal and run adb shell.
    * Once inside the shell, type su.
    * A Superuser request will appear on your AVD's screen. Grant the request.
    * The command prompt in your terminal should change from a `$` to a `#`, indicating you now have root privileges. 