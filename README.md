# HA-Configuration
My public HA creations


# My public HA Creations

## Table of contents

- [My public HA Creations](#my-public-ha-creations)
  - [Table of contents](#table-of-contents)
  - [Background](#background)
  - [Charging Pole](#charging-pole)
  - [Sonos Notification](#sonos-notifications)


___

## Background

I noticed a screenshot from a colleague showing his HA dashboard in which wrote a nice hack to give him some insights of the status of the nearby public charging poles. So I asked him to share some code with me, which he did. 

This is the result my adoption of his code to my HA instance. You can find the code [here](https://github.com/helmerzNL/HA-Configuration/tree/main/Packages/house/car). Feel free to re-use it.


## Charging Pole
When you download the code, please notice that you need to change the [resource](./Packages/house/car/laadpaal_rest.yaml) parameter. Visit [Nextcharge.app](https://nextcharge.app/) and look for the charging pole you would like to add.

![Look up Charging Pole](./images/laadpaal_howto_01.png)

Now, press (F12, to open the Developer Tools) and click the url to open it in a new tab. 

![Click URL](./images/laadpaal_howto_02.png)

Copy this url and paste it in the *resource* field in the [laadpaal_rest.yaml](./Packages/house/car/laadpaal_rest.yaml) file.

Now restart Home Assistant and create a card showing the created sensors.

![Laadpaal](./images/laadpaal01.png)

## Sonos Notification
I’ve been using Sonos speakers in my house quiet some time. In my early HA days I used Node-red for those notifications. But I found the time to recreate them in native HA automations. [Here](/Packages/notification/sonos_speaker_script.yaml) you can find the first version of the script. 

You can use the script by using my Automation example, which you can find [here](/Packages/_templates/sonos_notification_example_automation.yaml). Customize the defined variables any way you like, they will be passed on (and used) in the script.

**Variables**

- media_player_entity: media_player.*sonos_speaker*
- message_volume: *0.15*
- message: *This is an example sentence that is used.*
- message_timeout_hours: *0*
- message_timeout_minutes: *0*
- message_timeout_seconds: *4*
- message_timeout_milliseconds: *0*

*Note: The message_timeout is **required**, if you use Sonos speakers and don't use the timeout, the script (or automation) executes the next task right away and you don't hear the TTS* 