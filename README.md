# AiVA-96 for Google Assistant SDK on Android Things using RPi 3 (Windows 10)


The AiVA-96 for Google Assistant provides far-field voice capture using the XMOS XVF3000 voice processor.

This repository privides a simple guide how to install and test the Google Assistant on Android things using RPi 3. 

To find out more, visit: [wiziot]("https://wiziot")
and: [Google Assistant]("https://developers.google.com/assistant/sdk/guides/library/python/?hl=en")

---
## Pre-requirements

* AiVA-96 Board
* Raspberyy PI 3
* Micro SD Card / Micro SD Card Reader
* HDMI Display 

## Testing Environments
* Windows 10
* [Android Studio 3.0+][android_stduio]
    * [SDK Tool : 25.0.3 +][adnroid_sdk_manager]    
    * [SDK Platform : Android][adnroid_sdk_manager]

[android_stduio]:https://developer.android.com/studio/
[adnroid_sdk_manager]:https://developer.android.com/studio/intro/update#sdk-manager

* [Python3 latest Version]("https://www.python.org/getit/")

## Set up Assistant SDK Device
* [Get the Sample Source]("https://github.com/googlecodelabs/androidthings-googleassistant/archive/master.zip")

* [Configure a Developer Project and Account Settings]("https://developers.google.com/assistant/sdk/guides/library/python/embed/config-dev-project-and-account")
* [Register the Device Model]("https://developers.google.com/assistant/sdk/guides/library/python/embed/register-device")

* Configure the credentials
    * Install wheel script and google-auth-oauthlib
    <pre>
    <code>python -m pip install --upgrade pip setuptools wheel</code> 
    <code>python -m pip install --upgrade google-auth-oauthlib[tool] </code> </pre>

    * Add the google-oauth-tool installed path to Environment Variables.
    (c:\Users\user_id\AppData\Local\Programs\Python\Python37-32\Scripts\)
    * Open a command window on your developement machine (Windows 10) and follow the instruction to configure new credentials.json file
    <pre><code>
    google-oauthlib-tool --client-secrets c:\Users\user_id\Downloads\credentials.json --credentials \sample_sources\shared\src\main\res\raw\credentials.json --scope https://www.googleapis.com/auth/assistant-sdk-prototype –save 
    </code>
    </pre>


## Run the Starter Project
* Open Android Studio and import project
* Select the androidthings-googleassistant directory from the extracted zip file location
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





 










