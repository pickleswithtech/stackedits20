<!DOCTYPE html>
<html>

<head>
  <meta charset="utf-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Progress</title>
  <link rel="stylesheet" href="https://stackedit.io/style.css" />
</head>

<body class="stackedit">
  <div class="stackedit__left">
    <div class="stackedit__toc">
      
<ul>
<li>
<ul>
<li><a href="#install-ubuntu-touch-on-samsung-galaxy-s20-5g-made-by-sota4ever-on-github">Install Ubuntu Touch on Samsung Galaxy S20 5G (Made by Sota4Ever on Github)</a></li>
<li><a href="#step-1.-unlock-bootloader">Step 1. Unlock Bootloader</a></li>
<li><a href="#step-2.--set-binarys-to-custom">Step 2.  Set Binarys to Custom</a></li>
<li><a href="#step-3.-download-the-files-needed-to-buildcompile-the-kernel">Step 3. Download the files needed to build/compile the kernel</a></li>
<li><a href="#step-4.-buildcompile-the-kernel">Step 4. Build/Compile the kernel</a></li>
</ul>
</li>
</ul>

    </div>
  </div>
  <div class="stackedit__right">
    <div class="stackedit__html">
      <h2 id="install-ubuntu-touch-on-samsung-galaxy-s20-5g-made-by-sota4ever-on-github">Install Ubuntu Touch on Samsung Galaxy S20 5G <a href="https://github.com/Sota4Ever">(Made by Sota4Ever on Github)</a></h2>
<h3 id="preview-of-ubuntu-touch-running-on-the-s20-5g"><a href="https://github.com/pickleswithtech/SamsungS20UbuntuTouch/blob/halium-13/SamsungGalaxyS20.md">Preview of Ubuntu Touch running on the S20 5G</a></h3>
<h3 id="welcome-to-my-guide.-today-i-will-be-showing-you-how-to-compile-the-kernel-to-install-ubuntu-touch-on-a-samsung-galaxy-s20-5g-with-this-basic-guide.-lets-get-started">Welcome, to my guide. Today i will be showing you how to compile the kernel to install Ubuntu Touch on a Samsung Galaxy S20 5G with this basic guide. Let’s get started!</h3>
<h5 id="below-is-everything-you-need-for-installing-ubuntu-touch-on-a-s20-5g">Below is everything you need for installing Ubuntu Touch on a S20 5G</h5>
<h3 id="requirements">Requirements:</h3>
<ul>
<li>Samsung Galaxy S20 with an Unlocked Bootloader.</li>
<li>PC or Laptop or VM running <strong>The latest version of Ubuntu</strong> Get the <strong>Latest Version</strong> from <a href="https://ubuntu.com/download/desktop">here</a>.</li>
<li>Lots of patience</li>
<li>A USB-C to USB-A Cable (Standard Phone Charger)</li>
</ul>
<h2 id="step-1.-unlock-bootloader">Step 1. Unlock Bootloader</h2>
<p>For those who are new. I will give you a guide.</p>
<h3 id="step-1">Step 1</h3>
<p>Go to  <strong>Settings &gt; About phone</strong>  and tap  <strong>Build number</strong>  3 or more times to enable  <strong>Developer mode</strong>.</p>
<h3 id="step-2">Step 2</h3>
<p>Go back to  <strong>Settings</strong>, open  <strong>Developer options</strong>, and enable  <strong>OEM unlocking</strong>. Enter your password if prompted.</p>
<h3 id="step-3">Step 3</h3>
<p>Restart the device and quickly connect a  <strong>USB cable</strong> to your computer.</p>
<h3 id="step-4">Step 4</h3>
<p>While connecting, hold  <strong>Volume Up + Volume Down</strong>  buttons until you see a blue screen with text to enter. Congrats you are now in <strong>Odin Mode (Download Mode)</strong></p>
<h3 id="step-5">Step 5</h3>
<p>In <strong>Odin Mode</strong>, press the volume up button to  <strong>unlock the bootloader</strong>. The device will restart and reset to factory settings.</p>
<p>That’s it! Your device should say the bootloader is unlocked and the device is not trusted.</p>
<p>Image1 -</p>
<h2 id="step-2.--set-binarys-to-custom">Step 2.  Set Binarys to Custom</h2>
<p>If you have just Unlocked the Bootloader your binarys will be set to Samsung only because Samsung Knox still runs to set it to custom there’s two methods.</p>
<h3 id="method-1">Method 1</h3>
<p>Keep the phone on and connected to WIFI for at least a week.</p>
<h3 id="method-2">Method 2</h3>
<p>Use tools like Samfw to overwrite Samsung Knox. Below will be a guide for Samfw.</p>
<h3 id="samfw-method">Samfw Method</h3>
<ol>
<li>Download Samfw from <a href="https://samfw.com/SamFwToolSetup_v4.9.zip">here</a>. Your antivirus may flag the setup file. Don’t worry it’s safe I have tested it myself on my main PC. This is a windows app ONLY! Use Ubuntu for everything else!</li>
<li>After the setup is done open Samfw.</li>
<li>Then put your phone into test mode by typing *#0*# into the Phone app/Dialer</li>
</ol>
<h2 id="step-3.-download-the-files-needed-to-buildcompile-the-kernel">Step 3. Download the files needed to build/compile the kernel</h2>
<p>First on your PC or VM with <strong>The latest version of Ubuntu</strong>. Open your Terminal and enter <code>sudo apt update -y &amp;&amp; sudo apt install -y \ dialog bash sed wget git curl zip tar jq expect make cmake automake autoconf \ llvm lld lldb clang gcc binutils bison perl gperf gawk flex bc python3 \ zstd openssl unzip cpio build-essential ccache liblz4-tool libsdl1.2-dev \ libstdc++6 libxml2 libxml2-utils lzop pngcrush schedtool squashfs-tools \ xsltproc zlib1g-dev libncurses5-dev bzip2 gcc g++ libssl-dev \ gcc-aarch64-linux-gnu gcc-arm-linux-gnueabihf gcc-arm-linux-gnueabi \ libtinfo5 libelf-dev resolvconf dos2unix python3 python-is-python3 \ kmod neofetch android-tools-fsutils fakeroot pahole</code><br>
That command will download all the required files for compiling Ubuntu Touch for the Samsung S20 5G Kernel. Once the files finish downloading go to your Terminal again and run <code>git clone github.com/pickleswithtech/SamsungS20UbuntuTouch</code><br>
That command will clone the github repository you are viewing at the moment. Meaning you have all the files necessary to start compiling.</p>
<h2 id="step-4.-buildcompile-the-kernel">Step 4. Build/Compile the kernel</h2>
<h3 id="step-1-1">Step 1</h3>
<p>Once you are in the new directory from the command enter the following command into your Terminal <code>ln -s deviceinfo-x1s deviceinfo</code><br>
That command will set the device to the S20 5G.</p>
<h5 id="that-command-is-because-i-dont-want-to-change-the-code-made-by-sota4ever.">(That command is because I dont want to change the code made by Sota4Ever.)</h5>
<h3 id="step-2-1">Step 2</h3>
<p>After you set the deviceinfo to x1s enter the following command <code>./build.sh -b workdir</code><br>
That command will build some stuff for the next step. Wait for it to finish.</p>
<h3 id="step-3-1">Step 3</h3>
<p>Now, enter the following command <code>./build/prepare-fake-ota.sh out/device_**_usrmerge.tar.xz ota</code><br>
That will create the files for the next step.</p>
<h3 id="step-4-1">Step 4</h3>
<p>Once that other command finished run <code>./build/system-image-from-ota.sh ota/ubuntu_command images</code><br>
That command will prepare the image files. (.img) aaaaa</p>

    </div>
  </div>
</body>

</html>
