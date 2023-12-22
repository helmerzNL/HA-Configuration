# Notification Scripts

## Table of contents

- My Notification Solutions
  - [General](#general)
  - [iPhone Notification](#iphone-notification)
  - [Sonos Notification](#sonos-notification)
  - [Integrate iOS Alarm with Home Assistant](#integrate-ios-alarm-with-home-assistant)
  - [Buy Me A Coffee](#buy-me-a-coffee)


___

## General

I've created several notification scripts, so my Smart Home can deliver notifications. There are several ways that those notifications are being delivered:

* Audio - [Sonos Speakers](#sonos-notification)
* Push Notification - [Apple iOS](#iphone-notification)
* Message - [Microsoft Teams](#MSTeams)

Please note that all my scripts are delivers as-is, and probably need some adjustment or customization to get it working in your environment. If you really happy with the work I do, feel free to [Buy Me A Coffee](#buy-me-a-coffee).


## iPhone Notification
Since we only use iPhones in our house, I have created a [iPhone Notification script](/Packages/notification/iphone_script_v6.yaml) (which probably also works with Android phones btw). You can just call this script from an automation and are then asked to fill out the Fields with options (of which some are required, others are optional). 
One of the more interesting options, in my opinion, is the 'Wanneer Melden?' (Notify When?) field. This field gives you the option to only get an option when your device is in the 'Home' area. If you set this field to 'Away', you will get a notification whether you're at home or away. Comes in handy, when you are not at home and your spouse used the washing machine and receiving the 'washing machine is finished' notification does not make sense when you are not at home.

If you want to edit those fields, just Edit the script (when you've imported it) and update them with your own values (like the phones per person, or the actionable notification options). I've also included the [ios_event automation](/Packages/iOS_notifications_and_actions/ios_action_-_bmw_-_lock_car-blink_lights-sound_horn.yaml) automation, which you can use as an example. You can configure those actions in the iPhone script and after selection them, the iOS_event automation will cick in and perform the tasks configured there.


![iOS Actionable](./images/ios_actionable01.jpeg)

**Example**
I've had, again, included an example [here](/Packages/notification/iphone_service_example.yaml) that shows an example of a service that you could use in your automation.

## Integrate iOS Alarm with Home Assistant
Would it be nice if you could just configure the alarm on your iPhone and when it is time to go to bed, that time automatically syncs to your HA instance. And then in the morning, when your iPhone alarm goes off, your Sonos speaker starts playing music and your Philips HUE lights slowly turns on (and/or any other device you want to activate when you wake up).

On the official [HA Community forum](https://community.home-assistant.io/t/sync-next-ios16-alarm-clock-in-ha-with-shortcuts-and-companion-app/494726/62) I've found a way (with the help of some Apple Shortcuts) to achieve this. 

The configuration consists of two Shortcuts :

- [Configure HA Alarm](https://www.icloud.com/shortcuts/ee37cd7e90904b38a467a723279665a9) - Configures the Boolean in HA when 'Sleep mode' is turned on. 
- [Turn HA Alarm Off](https://www.icloud.com/shortcuts/ca72d93ecfc7405cab005059c6f0c97c) - Turns Off the Sonos/HUE when you turn off the iOS Alarm (when it sounds)

And a few automations and helpers, which you can find [here](/Packages/house/rooms/bedroom)

Please make sure you edit the Shortcuts to fit your needs:
- entity_id -> use your own input_boolean here, in the shortcut above it is set to input_datetime.ios_alarm (and in my scripts I use input_boolean.wekker_iphone)
- Label -> Edit the label where the Shortcut is looking for, in my example I use *Wekker*

## Sonos Notification
I’ve been using Sonos speakers in my house quiet some time, but with this Sonos Notification script I've made notifications a bit 'smarter'.
To use all features, please make sure you have [ESPresense](https://espresense.com) configured/in use in your house, since the *person priority* part makes use of ESPresense. If you use another solution to track occupancy of a room, you probably have to make some adjustments to the script.

[Here](/Packages/notification/sonos_speaker_script_v7.yaml) you can find the latest iteration of the script. 

You can use the script by using my Automation example, which you can find [here](/Packages/_templates/sonos_notification_example_automation.yaml). When you call the script from an automation, you can just fill out the required fields. If you speaker/room configuration is different, you would need to adjust the script before you can use it obviously. 

![Sonos Person Priority](/images/Sonos_notification_person_priority.png)

**Example**
I've included an example [here](Packages/notification/sonos_service_example.yaml) that will give you an example of a service you could include in your own automations.


*Note: I've included a few conditional actions that are used in combination with a Sonos soundbar and with a LG TV, which will show a toast message if the message has not priority. If you don't have a soundbar you can remove those actions.* 

When u have an Apple TV (or other media player) using the Sonos speaker for audio output, you will also need the [Helper](/Packages/notification/sonos_speaker_helper.yaml). If you don't have this setup (and you don't use one of the Sonos soundbars), you can remove the part in the script that checks (and sets) the input_boolean (marked with *##THIS PART IS ONLY REQUIRED IF YOU HAVE A SONOS SOUNDBAR AND YOU USE IT FOR TV/XBOX/MEDIAPLAYER AUDIO*).


## Microsoft Teams

*something for the future*

Please let me know if you have any questions.


## Buy me a Coffee

If you would like to thank me and think I deserve a coffee, fee fry to by me one. Thanks a lot!
<a href="https://www.buymeacoffee.com/HelmerNL" target="_blank"><img src="https://cdn.buymeacoffee.com/buttons/v2/default-yellow.png" alt="Buy Me A Coffee" height="41" width="174"></a>