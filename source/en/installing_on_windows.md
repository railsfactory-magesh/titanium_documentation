<summary>

This guide provides step-by-step instructions for installing Titanium on a Windows 7 system. You will learn how to:

* Satisfy all of Titanium's system requirements and software prerequisites
* Make the necessary changes to your environment configuration
* Test and troubleshoot your installation

</summary>

Getting Titanium Developer up and running successfully can be tricky when you aren't used to it. The following instructions aim to give you a comprehensive knowledge of the configuration procedure, and guide you through every stage.

# Pre-installation

## Log in as an Administrator

When you are developing your Android applications with Titanium on a daily basis, you will usually be logged into your Windows 7 system as a standard, non-administrative, user to help ensure it remains secure. However, to install components, configure system settings such as environment variables and apply software updates later on, you will require administrative privileges. Hence, for the following sections, log into the computer as an Administrator.

## Program Locations

The following table lists the respective locations of programs used by Titanium on our running system. As this installation is tried and tested, try to keep your program locations as similar as possible to these.

<table>
<tr>
  <th>Program</th><th>Location</th>
</tr>
<tr>
  <td>Python</td><td>C:\Program Files (x86)\Python27</td>
</tr>
<tr>
  <td>Git</td><td>C:\Program Files (x86)\Git</td>
</tr>
<tr>
  <td>SCons</td><td>C:\Program Files (x86)\Python27\Scripts</td>
</tr>
<tr>
  <td>Sun/Oracle JDK</td><td>C:\Program Files (x86)\Java\jdk1.6.0_23</td>
</tr>
<tr>
  <td>Android SDK Tools</td><td>C:\Program Files (x86)\Android\android-sdk-windows</td>
</tr>
<tr>
  <td>Titanium Developer</td><td>C:\Program Files (x86)\Titanium Developer</td>
</tr>
<tr>
  <td>Titanium Mobile SDKs</td><td>C:\ProgramData\Titanium\mobilesdk\win32</td>
</tr>
</table>

<info>
The convention on Windows 64bit Operating Systems is for 64bit software to be installed in the `C:&#92;Program Files&#92;` directory and 32bit software to be installed in `C:&#92;Program Files (x86)&#92;`. If you are installing on a 64bit OS, as we have for this guide, this portion of your program paths will remain the same as shown above.

If you are running 32bit Windows, only the `C:&#92;Program Files` directory will exist. Hence, you will need to bear this in mind, especially when configuring your environment variables.
</info>

## Projects Location

For demonstration purposes and convenience in this document, we have placed all our projects in the `C:&#92;Users&#92;&lt;USERNAME&gt;&#92;Desktop&#92;projects&#92;` directory. As storing user-generated data on the system drive like this is generally considered unwise, consider using a separate drive or disk partition instead. If you do, bear in mind that any files created by the administrator may not be writable by other users.

## Environment Variables

A number of software components require system variables to be set in order for them to function correctly with Titanium. This section provides a summary of those variables.

### PATH variable

The following locations must be *added* to your system `PATH`, separated by semi-colons. Obviously, the locations on your system may be slightly different.

<table>
<tr>
  <th>Program</th><th>Value appended to PATH Variable</th>
</tr>
<tr>
  <td>Python</td><td>C:\Program Files (x86)\Python27</td>
</tr>
<tr>
  <td>Git</td><td>C:\Program Files (x86)\Git\bin</td>
</tr>
<tr>
  <td>SCons</td><td>C:\Program Files (x86)\Python27\Scripts</td>
</tr>
<tr>
  <td>Sun/Oracle JDK</td><td>C:\Program Files (x86)\Java\jdk1.6.0_23\bin</td>
</tr>
<tr>
  <td>Android SDK</td><td>C:\Program Files (x86)\Android\android-sdk-windows\tools</td>
</tr>
</table>

### Software-specific variables

The following additional system variables must also be configured.

<table>
<tr>
  <th>Program</th><th>Variable Name</th><th>Variable Value</th>
</tr>
<tr>
  <td>JAVA_HOME</td><td>C:\Program Files (x86)\Java\jdk1.6.0_23</td>
</tr>
<tr>
  <td>android_sdk</td><td>C:\Program Files (x86)\Android\android-sdk-windows</td>
</tr>
</table>

### Configure system variables using the Control Panel

You may use the following process to configure system variables from the GUI.

* open the Windows Control Panel
* select **View by: Small icons** in the top, right-hand corner
* click the **System** icon

![screenshot](../assets/images/guides/install_windows/preinstallation/screenshot_01.png)

* select the **Advanced System Settings** option from the left pane

![screenshot](../assets/images/guides/install_windows/preinstallation/screenshot_02.png)

* select the **Advanced** tab at the top
* click the **Environment Variables** button

![screenshot](../assets/images/guides/install_windows/preinstallation/screenshot_03.png)

* use the **New** or **Edit** buttons at the bottom of the dialog to add or change system variables

![screenshot](../assets/images/guides/install_windows/preinstallation/screenshot_04.png)

# Installation

## Python

[Python](http://en.wikipedia.org/wiki/Python_%28programming_language%29) 2.6 or greater is required for Sun's JDK 6, and its 32bit version is required for SCons. Thus, download the current version of the **32bit Python** installer from the official [Python download page](http://www.python.org/download/) and run it.

* select "Install for all users"
* click the **Next** button

![screenshot](../assets/images/guides/install_windows/python/screenshot_01.png)

* Modify the destination directory to `C:&#92;Program Files (x86)&#92;Python27` (change `27` to reflect your Python version number)
* click the **Next** button

![screenshot](../assets/images/guides/install_windows/python/screenshot_02.png)

* ensure that all packages are selected for the installation, and that your system has enough free disk space to accommodate it
* click the **Next** button

![screenshot](../assets/images/guides/install_windows/python/screenshot_03.png)

* wait for the installation to complete

![screenshot](../assets/images/guides/install_windows/python/screenshot_04.png)

* click the **Finish** button to close the dialog

![screenshot](../assets/images/guides/install_windows/python/screenshot_05.png)

Refer to the [Environment variables](#environment_variables) section to configure the system `PATH` variable for **Python**.

## Git

[Git](http://en.wikipedia.org/wiki/Git_%28software%29) is needed in order to download, and stay up-to-date with, the latest Titanium KitchenSink from [our Github repository](https://github.com/appcelerator), which will be covered in a following section. Thus, download [msysGit](http://git-scm.com/download) and run the installer.

* click the **Next** button

![screenshot](../assets/images/guides/install_windows/git/screenshot_01.png)

* click the **Next** button

![screenshot](../assets/images/guides/install_windows/git/screenshot_02.png)

* browse to `C:&#92;Program Files (x86)&#92;Git` to set the destination directory
* click the **Next** button

![screenshot](../assets/images/guides/install_windows/git/screenshot_03.png)

* ensure that the following packages are selected for installation
* click the **Next** button

![screenshot](../assets/images/guides/install_windows/git/screenshot_04.png)

* leave the default "Git" text in the text field
* click the **Next** button

![screenshot](../assets/images/guides/install_windows/git/screenshot_05.png)

* select "Run Git from the Windows Command Prompt" radio button
* click the **Next** button

![screenshot](../assets/images/guides/install_windows/git/screenshot_06.png)

* select "Checkout as-is, commit as-is" radio button
* click the **Next** button

![screenshot](../assets/images/guides/install_windows/git/screenshot_07.png)

* wait for the installation to complete

![screenshot](../assets/images/guides/install_windows/git/screenshot_08.png)

* click the **Finish** button to complete the installation

![screenshot](../assets/images/guides/install_windows/git/screenshot_09.png)

Refer to the [Environment variables](#environment_variables) section to configure the system `PATH` variable for **Git**.

## SCons (optional)

[SCons](http://en.wikipedia.org/wiki/SCons) (Software Construction tool) is a build tool, similar to the classic `make` utility, used to compile Titanium projects such as [titanium_mobile](https://github.com/appcelerator/titanium_mobile). You can obtain it from the official [SCons download page](http://www.scons.org/download.php).

* run the SCons installer
* click the **Next** button

![screenshot](../assets/images/guides/install_windows/scons/screenshot_01.png)

* *provided* you have the 32bit rather than 64bit version of Python already installed, the installer should detect it, as follows
* click the **Next** button

![screenshot](../assets/images/guides/install_windows/scons/screenshot_02.png)

* click the **Next** button to begin installing the software

![screenshot](../assets/images/guides/install_windows/scons/screenshot_03.png)

* click the **Finish** button to complete the installation

![screenshot](../assets/images/guides/install_windows/scons/screenshot_04.png)

* note that the `scons` script is placed in the `Scipts` subdirectory of the Python directory, as shown

![screenshot](../assets/images/guides/install_windows/scons/screenshot_05.png)

Refer to the [Environment variables](#environment_variables) section to configure the system `PATH` variable for **SCons**.

## Sun/Oracle JDK

Android requires Sun's *32bit* Java Development Kit (JDK) in order to function. Be aware that no other JDK (such as OpenJDK) can be substituted for this, and the 64bit version of Sun's JDK will also not work.

* start by visiting [Sun's 32bit JDK](http://www.oracle.com/technetwork/java/javase/downloads/index.html) download page, clicking on the "Download JDK" button and selecting **Windows** (rather than **Windows x64**) from the list of platforms

![screenshot](../assets/images/guides/install_windows/jdk/screenshot_01.png)

* once downloaded, start the installer
* click the **Next** button

![screenshot](../assets/images/guides/install_windows/jdk/screenshot_02.png)

* deselect **Source Code** from the list of packages to install
* take a note of the **Install to** directory
* click the **Next** button

![screenshot](../assets/images/guides/install_windows/jdk/screenshot_03.png)

* wait for the installation to complete

![screenshot](../assets/images/guides/install_windows/jdk/screenshot_04.png)

* at the Java Runtime Environment (JRE) setup screen, take a note of the **Install to** directory, for future reference
* click the **Next** button

![screenshot](../assets/images/guides/install_windows/jdk/screenshot_05.png)

* wait for the installation to complete (the dialog should close automatically)

![screenshot](../assets/images/guides/install_windows/jdk/screenshot_06.png)

Refer to the [Environment variables](#environment_variables) section to set the system `JAVA_HOME` variable to the base JDK directory, and add the JDK `bin` (binaries/executables) directory to the system `PATH`.

## Android SDK Tools

The Android SDK is required in order for Titanium Mobile to boot Android emulators and launch your applications to them. Thus, download the [Android SDK](http://developer.android.com/sdk/index.html) installer. In case you need them, refer to the official [System Requirements](http://developer.android.com/sdk/requirements.html) and [Installing the SDK](http://developer.android.com/sdk/installing.html) documents.

* run the Android SDK installer
* click the **Next** button

![screenshot](../assets/images/guides/install_windows/android_sdk/screenshot_01.png)

* ensure that the installer has recognized the Sun JDK 1.6 software that you installed in the previous section
* click the **Next** button

![screenshot](../assets/images/guides/install_windows/android_sdk/screenshot_02.png)

* note the **Destination Folder**, so that you can use it to set the required environment variables later on
* ensure that there is sufficient space required for the installation

![screenshot](../assets/images/guides/install_windows/android_sdk/screenshot_03.png)

* leave the default "Android SDK Tools" text in the text field
* click the **Install** button

![screenshot](../assets/images/guides/install_windows/android_sdk/screenshot_04.png)

* wait for the installation to complete
* click the **Next** button

![screenshot](../assets/images/guides/install_windows/android_sdk/screenshot_05.png)

* click the **Finish** button to complete the installation

![screenshot](../assets/images/guides/install_windows/android_sdk/screenshot_06.png)

Refer to the [Environment variables](#environment_variables) section to configure the system `android-sdk` variable for the **Android SDK Home** and the `PATH` variable for **Android SDK Tools**.

## Android Packages

### Google-developed SDKs

Once the *Android SDK Tools* software has been installed, as explained in the [previous section](file:///home/personal/dowsep/projects/development/titanium_documentation/output/en/installing_on_windows.html#android_sdk_tools), you need to install its platform SDKs and their related tools.

* launch the *Android SDK and AVD Manager* by running `android` from the command line
* ensure the following packages are selected, which represent Titanium's supported platforms at the time of writing
* select the **Accept All** radio button
* click the **Install** button to download and install the selected packages

![screenshot](../assets/images/guides/install_windows/android_packages/screenshot_01.png)

* wait for the download and installation to complete

![screenshot](../assets/images/guides/install_windows/android_packages/screenshot_02.png)

* click the **Yes** button to restart ADB

![screenshot](../assets/images/guides/install_windows/android_packages/screenshot_03.png)

* click the **Close** button

![screenshot](../assets/images/guides/install_windows/android_packages/screenshot_04.png)

### Third-party SDKs

So far, you have only installed Google's own, standard, SDKs. Now you can install the third-party APIs and tools, which includes Google's enhanced APIs that provide advanced features such as support for maps.

![screenshot](../assets/images/guides/install_windows/android_packages/screenshot_05.png)

* select the **Available packages** category in the left panel
* ensure that the **Display updates only** checkbox is enabled
* ensure that the following packages are selected in the right panel
* click the **Install Selected** button

![screenshot](../assets/images/guides/install_windows/android_packages/screenshot_06.png)

* select the **Accept All** radio button
* click the **Install** button to download and install the selected packages

![screenshot](../assets/images/guides/install_windows/android_packages/screenshot_07.png)

* wait for the download and installation to complete

![screenshot](../assets/images/guides/install_windows/android_packages/screenshot_08.png)

* click the **Yes** button to restart ADB

![screenshot](../assets/images/guides/install_windows/android_packages/screenshot_09.png)

* click the **Close** button to complete the installation

![screenshot](../assets/images/guides/install_windows/android_packages/screenshot_10.png)

* double-check that your package list resembles the following

![screenshot](../assets/images/guides/install_windows/android_packages/screenshot_11.png)

<warning>Whenever you install or remove packages, it is vital to delete all the existing AVDs listed in the **Virtual devices** category. As this is so important, check it now to get into the habit.  See screen below</warning>

![screenshot](../assets/images/guides/install_windows/android_packages/screenshot_12.png)

## Workaround for a missing `adb`
<info>Due to a recent change in the Android SDK file structure, Titanium Developer expects the `adb.exe` executable to be in `path&#92;to&#92;android-sdk-windows&#92;tools` whereas it currently resides in `path&#92;to&#92;android-sdk-windows&#92;platform-tools`. To fix this, use the following step.
</info>

* create a symbolic link for `adb.exe` and `AdbWinApi.dll`, its associated dynamic link library, as follows:

<code>
cd C:\Program Files (x86)\Android\android-sdk-windows\tools
mklink adb.exe ..\platform-tools\adb.exe
mklink AdbWinApi.dll ..\platform-tools\AdbWinApi.dll
</code>

![screenshot](../assets/images/guides/install_windows/android_packages/screenshot_13.png)

If, for some reason, you cannot create a symbolic link, you can simply copy `adb.exe` and `AdbWinApi.dll` to the tools directory. Bear in mind that, unlike the symbolic link method, you will need to repeat this process whenever you install a package that applies an update to either of these files.

## Titanium Developer

Once all the pre-requisites described above have been installed, and the environment variables configured, you are ready to install *Titanium Developer*. Obtain the installer from the [download page](http://www.appcelerator.com/products/download) and then run it.

### Install Titanium Developer

* click the **Next** button

![screenshot](../assets/images/guides/install_windows/titanium/screenshot_01.png)

* read the license agreement and select the checkbox to accept its terms
* click the **Next** button

![screenshot](../assets/images/guides/install_windows/titanium/screenshot_02.png)

* ensure the **Install Titanium Developer to** text field is set to the following
* click the **Next** button

![screenshot](../assets/images/guides/install_windows/titanium/screenshot_03.png)

* click the **Install** button to begin the installation

![screenshot](../assets/images/guides/install_windows/titanium/screenshot_04.png)

* wait for the installation to complete

![screenshot](../assets/images/guides/install_windows/titanium/screenshot_05.png)

* click the **Finish** button to complete the installation

![screenshot](../assets/images/guides/install_windows/titanium/screenshot_06.png)

### Configure Titanium Developer

While you will ordinarily run Titanium Developer from your standard user account, you will need to run it as administrator to download and apply its updates.

* launch *Titanium Developer* using the Desktop or Start Menu icon
* *Sign Up* or *Login* and fill in your details to proceed

![screenshot](../assets/images/guides/install_windows/titanium/screenshot_07.png)

* click the **Profile** button in the top left of the screen
* complete the **First Name** and **Last Name** fields
* configure the **Android SDK** field by browsing to `C:&#92;Program Files (x86)&#92;Android&#92;android-sdk-windows`
* click the **Save Profile** button

![screenshot](../assets/images/guides/install_windows/titanium/screenshot_09.png)

### Update Titanium Developer

A banner at the top of Titanium Developer will notify you if there are any published updates that need to be installed. It's best to apply the updates as explained below, and then restart the application and repeat the process for every new update banner until they have all been cleared.

* click on the **New Mobile SDK available** link

![screenshot](../assets/images/guides/install_windows/titanium/screenshot_08.png)

* wait for the download and installation to complete

![screenshot](../assets/images/guides/install_windows/titanium/screenshot_10.png)

* restart *Titanium Developer*
* repeat the previous two steps

![screenshot](../assets/images/guides/install_windows/titanium/screenshot_11.png)

## Test a default project

When all the components have been installed exactly as described in the previous sections, it is wise to check that Titanium works correctly by creating and booting a default, unmodified, project.

* click on the **New Project** button at the top of **Titanium Developer**
* select **Project type: Mobile**
* enter an application name to the **Name** field (ie testapp1)
* enter an application id to the **App Id** field (ie com.mydomain.testapp1)
* browse to your projects directory (you don't need to include the application name in the path) in the **Directory** field
* enter your website to the **Company/Personal URL** field
* ensure that **Android SDK Found** shows a green tick
* click on the **Create Project** button

![screenshot](../assets/images/guides/install_windows/default_project/screenshot_01.png)

* using Windows Explorer, you can see that a project directory for your application has been created

![screenshot](../assets/images/guides/install_windows/default_project/screenshot_02.png)

* select a project in the left pane and click the **Edit** tab
* use the **Titanium SDK** to select the newly-installed SDK

![screenshot](../assets/images/guides/install_windows/default_project/screenshot_03.png)

* click on the **Test & Package** tab at the top
* ensure the latest-supported Android SDK is selected (which is **APIs 2.2** at the time of writing [Jan2011])
* choose a suitable emulator display resolution in the **Screen** field (ie WVGA800)
* click the **Launch** button

![screenshot](../assets/images/guides/install_windows/default_project/screenshot_04.png)

* wait for the emulator to boot
* to unlock the emulator, click and hold the padlock icon with the mouse and drag it over the speaker icon, and release

![screenshot](../assets/images/guides/install_windows/default_project/screenshot_05.png)

The emulator should boot and the application should launch. If either of these does not happen, please refer to the [Troubleshoot](#troubleshoot) section below, the [Troubleshooting Your Installation](http://developer.appcelerator.com/guides/en/troubleshooting_your_installation.html) guide or seek assistance in the [Q&A](http://developer.appcelerator.com/questions/created) forum.

![screenshot](../assets/images/guides/install_windows/default_project/screenshot_06.png)

## Titanium SDKs

Official releases of Titanium's SDKs will be made available via the Titanium Developer update banner, as explained in the previous section. However, our core developers write enhancements and fix bugs every single day, and often you will want to take advantage of these improvements.

Daily code updates are available in source code form from the our [Github repository](https://github.com/appcelerator) or compiled and packaged from our [Continuous Builds](http://builds.appcelerator.com.s3.amazonaws.com/index.html) website.

<warning>
Be aware that only **major** releases of any of our software are officially supported. If you find a problem with a *Continuous Build* or *compiled* SDK, and are unable to find a resolution for it from our [Lighthouse]() bug-tracking system or the [Q&A](http://developer.appcelerator.com/questions/created), simply try each previous day's release until you find one that works.
</warning>

<info>
After downloading a *Continuous Build SDK*, it's important to check the SHA1 hash of the file to confirm it is not corrupt. We use [Hashtab](http://beeblebrox.org/) for this purpose although, obviously, your choice to use it is done so at your own risk.
</info>

### Locate your local Titanium SDK directory

Once you have a Titanium SDK archive, simply extract it to your local SDK directory and restart Titanium Developer to install it.

On Windows, the directory where the Titanium SDKs are installed is hidden by default, so follow these steps to find it.

* open the Windows Control Panel
* select **View by: Small icons** in the top, right-hand corner
* click the **Folder Options** icon

![screenshot](../assets/images/guides/install_windows/continuous_build/screenshot_01.png)

* select the **View** tab
* in the **Advanced settings** list, select the **Show hidden files, folders, and drives** radio button
* click the **OK** button

![screenshot](../assets/images/guides/install_windows/continuous_build/screenshot_02.png)

It will now be possible to navigate to the `C:&#92;ProgramData&#92;Titanium&#92;mobilesdk&#92;win32` directory, where Titanium SDKs are stored

### Install a Titanium SDK Continuous Build

* download a **Windows (Android only)** SDK from the Titanium SDK [Continuous Builds](http://builds.appcelerator.com.s3.amazonaws.com/index.html) website. Extract it somewhere convenient. It is advisable to rename the `mobilesdk&#92;win32&#92;&lt;version&gt;&#92;` directory to reflect the SDK's version and date, ie `1.5.X-20110111`)
* open Windows Explorer
* navigate to `C:&#92;ProgramData&#92;Titanium&#92;mobilesdk&#92;win32&#92;`, and move your renamed SDK directory to this location

![screenshot](../assets/images/guides/install_windows/continuous_build/screenshot_05.png)

* launch or restart Titanium Developer
* select a project in the left pane and click the **Edit** tab
* use the **Titanium SDK** field to select the newly-installed SDK

![screenshot](../assets/images/guides/install_windows/continuous_build/screenshot_06.png)

* click on the **Test & Package** tab at the top
* ensure the latest-supported Google SDK is selected (which is **APIs 2.2** at the time of writing [Jan2011])
* choose a suitable emulator display resolution in the **Screen** field (ie WVGA800)
* click the **Launch** button

![screenshot](../assets/images/guides/install_windows/continuous_build/screenshot_07.png)

* wait for the emulator to boot
* to unlock the emulator, click and hold the padlock icon with the mouse and drag it over the speaker icon, and release

![screenshot](../assets/images/guides/install_windows/continuous_build/screenshot_08.png)

The emulator should boot and the application should launch. If either of these does not happen, please refer to the [Troubleshoot](#troubleshoot) section below, the [Troubleshooting Your Installation](http://developer.appcelerator.com/guides/en/troubleshooting_your_installation.html) guide or seek assistance in the [Q&A](http://developer.appcelerator.com/questions/created) forum.

![screenshot](../assets/images/guides/install_windows/continuous_build/screenshot_09.png)

# Use

Now all the setup steps are complete, you can begin importing and creating projects and developing your own applications.

## Log in as a Standard User

To help keep computers secure, it is generally accepted that they should normally be operated using a non-administrative user. Hence, log in to your system using your own user account. Then create your [projects directory](#projects_location), where you will store all of your Titanium-related data.

## Test a default project (again)

To confirm that Titanium works just as well under a standard user account as it does as the Administrator, follow the earlier steps to [create a default project](#test_a_default_project).

## Titanium's KitchenSink

The *KitchenSink* is a Titanium application that is used to demonstrate and test all Titanium's fundamental features. It is available within our [titanium_mobile](https://github.com/appcelerator/titanium_mobile/) Github repository, in the `&#47;demos&#47;KitchenSink&#47;` directory.

## Clone the `titanium_mobile` repository using Git

* start a Windows command line session, by clicking on `Start Menu &#47; All Programs &#47; Accessories &#47; Command Prompt`
* enter the following commands:

<code>
cd desktop/projects
git clone git://github.com/appcelerator/titanium_mobile.git
</code>

![screenshot](../assets/images/guides/install_windows/kitchensink/screenshot_01.png)

* wait for `git` to complete the transfer

![screenshot](../assets/images/guides/install_windows/kitchensink/screenshot_02.png)

* click on the **Import Project** button at the top
* browse to the local `titanium_mobile` repository, at `C:&#92;Users&#92;&lt;USERNAME&gt;&#92;Desktop&#92;projects&#92;`

![screenshot](../assets/images/guides/install_windows/kitchensink/screenshot_03.png)

* inside the local `titanium_mobile` repository, browse to the `&#47;demos&#47;KitchenSink&#47;` directory

![screenshot](../assets/images/guides/install_windows/kitchensink/screenshot_04.png)

* select the version of the Titanium SDK that reflects the branch of the repository that is currently checked out (by default this will be `master`, which is the development branch of the codebase)

<info>
To checkout a different branch of the repository that holds a version of the KitchenSink that is compatible with the Titanium SDK version you are using, perform the following steps at the command line:

  <code>
  cd desktop/projects/titanium_mobile
  git branch [show current branch]
  git branch -a [show all available branches]
  git checkout 1_5_X [checkout 1_5_X for use with Titanium 1.5.X SDKs]
  </code>

</info>

![screenshot](../assets/images/guides/install_windows/kitchensink/screenshot_05.png)

* click on the **Test & Package** tab at the top
* ensure the latest-supported Android SDK is selected (which is **APIs 2.2** at the time of writing [Jan2011])
* choose a suitable emulator display resolution in the **Screen** field (ie WVGA800)
* click the **Launch** button

![screenshot](../assets/images/guides/install_windows/kitchensink/screenshot_06.png)

* wait for the emulator to boot
* to unlock the emulator, click and hold the padlock icon with the mouse and drag it over the speaker icon, and release

![screenshot](../assets/images/guides/install_windows/kitchensink/screenshot_07.png)

The emulator should boot and the application should launch. If either of these does not happen, please refer to the [Troubleshoot](#troubleshoot) section below, the [Troubleshooting Your Installation](http://developer.appcelerator.com/guides/en/troubleshooting_your_installation.html) guide or seek assistance in the [Q&A](http://developer.appcelerator.com/questions/created) forum.

![screenshot](../assets/images/guides/install_windows/kitchensink/screenshot_08.png)

# Troubleshoot


## Installation updates fail

On-access antivirus software can interfere with Titanium downloads. If the installation progress meter appears to stall, try disabling your antivirus for the duration of the download and installation.

Alternatively, your machine may be behind a proxy server. See the [following section](#proxy_needs_to_be_manually_configured).

## Cannot login to Titanium Developer

Your machine may be behind a proxy server. See the [following section](#proxy_needs_to_be_manually_configured).

## Proxy needs to be manually configured

When your machine is behind a [proxy server](http://en.wikipedia.org/wiki/Proxy_server), Titanium Developer attempts to automatically detect your proxy settings based on your platform. If you suspect this process has not been successful, you can manually configure your the settings using the following system environment variables:

* HTTP_PROXY
* HTTPS_PROXY
* FTP_PROXY
* SOCKS_PROXY

These should be set to the address of the server. Ask your network administrator if you don't know them.

## Missing adb

See the [workaround for a missing adb](#workaround_for_a_missing_%3Ctt%3Eadb%3C/tt%3E) section.

## Run Emulator Screen "Loading..."

If you are not able to boot an emulator, and the **Screen** drop-down menu on your **Run Emulator** tab always shows "Loading..." as in the image below, refer to ticket [#2813](https://appcelerator.lighthouseapp.com/projects/32238-titanium-mobile/tickets/2813) for a possible solution.

![screenshot](../assets/images/guides/install_windows/troubleshoot/screenshot_01.png)
