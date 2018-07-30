# AiVA-96 for Google Assistant SDK on Android Things using RPi 3 (Windows 10)


The AiVA-96 for Google Assistant provides far-field voice capture using the XMOS XVF3000 voice processor.

This repository privides a simple guide how to install and test the Google Assistant on Android things using RPi 3 and AiVA-96 board. 

To find out more, visit: <a ref = "https://wiziot">wiziot</a>
and: <a ref ="https://developers.google.com/assistant/sdk/guides/library/python/?hl=en">  Google Assistant</a>

---
## Pre-requirements

* AiVA-96 Board
* Raspberyy PI 3
* Micro SD Card / Micro SD Card Reader
* HDMI Display 
## Hardware Setup
* Setup your hardware by following the Hardware Setup at: https://wiziot home page
## Testing Environments
* Host PC : Windows 10
* [Android Studio 3.0+][android_stduio]
    * [SDK Tool : 25.0.3 +][adnroid_sdk_manager]    
    * [SDK Platform : Android][adnroid_sdk_manager]

[android_stduio]:https://developer.android.com/studio/
[adnroid_sdk_manager]:https://developer.android.com/studio/intro/update#sdk-manager

* <a href = "https://www.python.org/getit/"> Python3 latest Version</a>

## Set up Assistant SDK Device
* <a href = "https://developer.android.com/things/hardware/raspberrypi"> Install Android Things on RPi 3</a>
* <a href = "https://github.com/googlecodelabs/androidthings-googleassistant/archive/master.zip">Get the Sample Source</a>

* <a href = "https://developers.google.com/assistant/sdk/guides/library/python/embed/config-dev-project-and-account">Configure a Developer Project and Account Settings</a>
* <a href = "https://developers.google.com/assistant/sdk/guides/library/python/embed/register-device">Register the Device Model</a>

* Configure the credentials
    * Install wheel script and google-auth-oauthlib
    <pre>
    <code>python -m pip install --upgrade pip setuptools wheel</code> 
    <code>python -m pip install --upgrade google-auth-oauthlib[tool] </code> </pre>

    * Add google-oauth-tool installed path to Environment Variables.
    (c:\Users\user_id\AppData\Local\Programs\Python\Python37-32\Scripts\)
    * Open a command window on your developement machine (Windows 10) and follow the instruction to configure new credentials.json file
    <pre><code>
    google-oauthlib-tool --client-secrets \ c:\Users\user_id\Downloads\credentials.json --credentials \new_folder\credentials.json --scope \ https://www.googleapis.com/auth/assistant-sdk-prototype –save 
    </code>
    </pre>


## Run the Starter Project
* Open Android Studio and import project
* Select the androidthings-googleassistant directory from the extracted zip file location
* Move '/new_folder/credentials.json' file to '\sample_sources\shared\src\main\res\raw\' folder 
* Open the step1-start-here module
* Setup Device Config
    * Connect ADB Device (Raspberry PI 3)
    <pre><code>
    adb connect your_device_ip    
    </code></pre>
    * Modify the Source file (AssistantAcitivy.java)

        private static final boolean USE_VOICEHAT_DAC = true → **false**; 
* Run the Application 
    * Run -> Run 'step1-start-here' from the menu.
    * Select the board that start with **Iot_** from the device chooser dialog. 
    * Press a button to start recording your request.
    * Say 'Hi'
    * Release the button when finished talking.
    * The goole assistant answer should playback on the speaker.





 










