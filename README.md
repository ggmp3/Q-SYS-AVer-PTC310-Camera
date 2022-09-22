# Q-SYS-AVer-PTC310-Camera


## NOTES:
- Audio Encoding Type control has been included (combo box) but only one option is available (AAC) for visibility. The camera does not have any set/get request to modify this. Only AAC is available for encoding audio.
- Have NOT added any of the 'Sleep Timer' functions on the System page as these are only available when video streaming is USB Only.


### 17th August 2022 - Glen Gorton
Updated for AVer PTC310U and PTC310H cameras running firmware v0.0.0000.45
Additional functions added by Glen Gorton (glen.gorton@gmail.com)

Added to GetUnitInfoNetwork() function that uses "GetString=":
- 'NDI Local Device Name' text box
- 'NDI Device Channel' (Camera ID) text box
- 'NDI Receive Group' text box
- 'NDI Multicast Server Mask' text box
- 'NDI Multicast Server Address' text box
- 'NDI Discovery Server Address' text box

Added to Poll() function that uses "Get=":
- 'NDI Reliable UDP' toggle
- 'NDI Discovery Server' toggle
- 'NDI Multicast Server' toggle
- 'NDI Multicast TTL' integer knob. (1 to 255)


### 24th June 2022 - Jason Foord
- Change 'Sync' terminology to 'Poll'
- Refactored EventHandlers to start pollDelay Timer instead of Poll directly - fixes rapid calling of Poll function when spamming eventhandlers.
- StartPollDelay() function starts the pollDelay Timer
- added panTimer and tiltTimer to prevent fader spam of pan and tilt speed. Will now only send one post request after the timer settles (200ms)
- Changed HttpDownload timeout from 2s to 5s


### 7th June 2022
Updated for AVer PTC310U and PTC310H cameras running firmware v0.0.0000.43
Additional functions added by Glen Gorton (glen.gorton@gmail.com)

- 'USB Audio' off/on toggle added.
- 'USB Connected' status LED added. Response: 0(plug out), 1(plug in)
- 'UVC Stream' (UVC Status) LED added. Response: 0(stream off), 1(stream on)
- 'Focus Near Limit' added.
- 'Auto Focus Mode' selection added. (Continuous AF, or AF Trigger After PTZ)


### 20th May 2022
Tested with AVer PTC310U and PTC310H cameras running firmware v0.0.0000.42
Component originally written by Jason Foord (jf@tag.com.au) at TAG Austalia.

Additional functions added by Glen Gorton (glen.gorton@gmail.com)
- ‘Hybrid’ Tracking Mode now selectable.
- ‘Video Freeze while Preset’ now selectable.
- ‘Preset Speed’ now adjustable.
- ‘Zoom Speed’ corrected to be ‘High / Low’ choices.
- ‘Digital Zoom’ on/off toggle added.
- ‘Digital Zoom Limit’ (2-12x zoom) added.
- ‘MCU Firmware Version’ and ‘Lens Firmware Version’ info added.
- ‘Relative Zoom Ratio’ now selectable.
- ‘Preset Affects PTZ & Focus Values Only’ now selectable.
- ‘Status OSD’ on/off now selectable.
- ‘Power On To Preset’ and ‘Power Up To Preset’ now selectable.
- ‘Preset Accuracy’ now selectable (firmware v0.0.0000.42)
- ‘Language’ selection now selectable.
- ‘Reboot’ trigger added.
- ‘Power Frequency’ now selectable.
- ‘Video Priority Mode’ now selectable.
- ‘Video Output Resolution’ now selectable.
- ‘Video Mode’ now selectable.
- ‘Stream Video Output’ resolution now selectable.
- ‘Stream Bitrate’ now adjustable.
- ‘Stream Encoding Type’ now selectable.
- ‘Stream Framerate’ now adjustable.
- ‘Stream I-VOP Interval’ now adjustable.
- ‘Stream Rate Control’ now adjustable.
- ‘Audio Input Type’ now selectable.
- ‘Audio Encoding Type’ added if further options (other than AAC become available - see Notes)
- ‘Audio Volume’ now adjustable.
- ‘Audio Sampling Rate’ now adjustable.
- ‘Hostname’ now visible and modifiable.
- ‘DHCP’ status now visible.
- ‘White Balance Mode’, ‘R Gain’ ‘B Gain’, ‘One Push Set’ selectable/adjustable.
- ‘Saturation’, ‘Contrast’, ‘Sharpness’ now adjustable.
- ‘Noise Filter’, ‘Image Mirror’, ‘Image Flip’ now adjustable.
- ‘Exposure Mode’, ‘Slow Shutter’, ‘WDR’ now selectable.
- ‘Exposure Value’, Shutter Speed’, Iris Level’, ‘Gain Level’, ‘Gain Limit Level’, ‘BLC’ now adjustable.
- ‘Tracking Sensitivity’, ‘Tracking Idle Time’, ‘Effective Tracking Area’, ‘People Size’, ‘Tracking Auto Zoom’, ‘Tracking Auto Tilt’ now adjustable.
- ‘RTMP Server URL’, ‘RTMP Stream Key’, ‘RTMP Stream Status’, ‘RTMP Start/Stop Stream’ config added. Testing required.
- ‘RTSP Security’ can now be toggled.
- ‘SRT Destination IP’, ‘SRT Port’, ‘SRT Latency’, ‘SRT Encryption’, ‘SRT Passphrase’, ‘SRT Connection Status’, ‘SRT Start/Stop Stream’ config added.