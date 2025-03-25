

## Install Ubuntu Touch on Samsung Galaxy S20 5G [(Made by Sota4Ever on Github)](https://github.com/Sota4Ever)
### [Preview of Ubuntu Touch running on the S20 5G](https://github.com/pickleswithtech/SamsungS20UbuntuTouch/blob/halium-13/SamsungGalaxyS20.md) 
### Welcome, to my guide. Today i will be showing you how to compile the kernel to install Ubuntu Touch on a Samsung Galaxy S20 5G with this basic guide. Let's get started!

##### Below is everything you need for installing Ubuntu Touch on a S20 5G

   ### 	Requirements:								
   

 - Samsung Galaxy S20 with an Unlocked Bootloader.
 - PC or Laptop or VM running **The latest version of Ubuntu** Get the **Latest Version** from [here](https://ubuntu.com/download/desktop).
 - Lots of patience
 - A USB-C to USB-A Cable (Standard Phone Charger) 

## Step 1. Unlock Bootloader

For those who are new. I will give you a guide.
### Step 1
Go to  **Settings > About phone**  and tap  **Build number**  3 or more times to enable  **Developer mode**.
### Step 2
Go back to  **Settings**, open  **Developer options**, and enable  **OEM unlocking**. Enter your password if prompted.
 ### Step 3
Restart the device and quickly connect a  **USB cable** to your computer.
### Step 4
While connecting, hold  **Volume Up + Volume Down**  buttons until you see a blue screen with text to enter. Congrats you are now in **Odin Mode (Download Mode)**
### Step 5
In **Odin Mode**, press the volume up button to  **unlock the bootloader**. The device will restart and reset to factory settings.

That's it! Your device should say the bootloader is unlocked and the device is not trusted.

Image1 - 

## Step 2.  Set Binarys to Custom
If you have just Unlocked the Bootloader your binarys will be set to Samsung only because Samsung Knox still runs to set it to custom there's two methods.
### Method 1
Keep the phone on and connected to WIFI for at least a week.
### Method 2
Use tools like Samfw to overwrite Samsung Knox. Below will be a guide for Samfw.
### Samfw Method
1. Download Samfw from [here](https://samfw.com/SamFwToolSetup_v4.9.zip). Your antivirus may flag the setup file. Don't worry it's safe I have tested it myself on my main PC. This is a windows app ONLY! Use Ubuntu for everything else!
2. After the setup is done open Samfw.
3. Then put your phone into test mode by typing \*#0*# into the Phone app/Dialer
## Step 3. Download the files needed to build/compile the kernel
First on your PC or VM with **The latest version of Ubuntu**. Open your Terminal and enter `sudo apt update -y && sudo apt install -y \
    dialog bash sed wget git curl zip tar jq expect make cmake automake autoconf \
    llvm lld lldb clang gcc binutils bison perl gperf gawk flex bc python3 \
    zstd openssl unzip cpio build-essential ccache liblz4-tool libsdl1.2-dev \
    libstdc++6 libxml2 libxml2-utils lzop pngcrush schedtool squashfs-tools \
    xsltproc zlib1g-dev libncurses5-dev bzip2 gcc g++ libssl-dev \
    gcc-aarch64-linux-gnu gcc-arm-linux-gnueabihf gcc-arm-linux-gnueabi \
    libtinfo5 libelf-dev resolvconf dos2unix python3 python-is-python3 \
    kmod neofetch android-tools-fsutils fakeroot pahole
`
 That command will download all the required files for compiling Ubuntu Touch for the Samsung S20 5G Kernel. Once the files finish downloading go to your Terminal again and run `git clone github.com/pickleswithtech/SamsungS20UbuntuTouch`
That command will clone the github repository you are viewing at the moment. Meaning you have all the files necessary to start compiling.

## Step 4. Build/Compile the kernel
### Step 1
Once you are in the new directory from the command enter the following command into your Terminal `ln -s deviceinfo-x1s deviceinfo`
That command will set the device to the S20 5G.
##### (That command is because I dont want to change the code made by Sota4Ever.) 
### Step 2
After you set the deviceinfo to x1s enter the following command `./build.sh -b workdir` 
That command will build some stuff for the next step. Wait for it to finish.
### Step 3
Now, enter the following command `./build/prepare-fake-ota.sh out/device_**_usrmerge.tar.xz ota`
That will create the files for the next step.
### Step 4
When that has finished run `./build/system-image-from-ota.sh ota/ubuntu_command images`
That command will prepare the image files (.img).

If you done it all correctly you will have the following files!

 - rootfs.img
- dtbo.img (not necessary)
- system.img (not necessary)
- boot.img
# Step 5. Install the files
First, we need to install TWRP (Team Win Recovery Project)
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE5MjMwODI0NDQsMTY3Mjg2MDg0OV19
-->