# My public HA Creations

## Table of contents

- [My public HA Creations](#my-public-ha-creations)
  - [Background](#background)
  - [Charging Pole](#charging-pole)
  - [Charge Reminder](#charge-reminder)
  - [Notification Scripts](#notification-scripts)
  - [Buy Me A Coffee](#buy-me-a-coffee)

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

## Charge Reminder
Get a reminder when you don't have enough range in your (car) battery left to drive to your next appointment (and back home). To use this automation, there are a few requirements that need to be in place:
* A calendar (I'm using the [Office 365 integration](https://rogerselwyn.github.io/O365-HomeAssistant/) through HACS) integrated in Home Assistant
* The [Waze Travel Time](https://www.home-assistant.io/integrations/waze_travel_time) integration

Besides these two integrations, it makes use of two of my notification scripts:
* [iPhone Notification v6](/Packages/notification/iphone_script_v6.yaml)
* [Sonos Notofication v6](/Packages/notification/sonos_speaker_script_v6.yaml)

You can find the concept version of the scripts [here](/Packages/car/)

*this is work in progress*


## Notification Scripts
I've created some custom iOS and Sonos notification scripts, which you can find [here](/Packages/notification/). On this page you can also find the custom *iOS Alarm* script.


Please let me know if you have any questions.

## Buy me a Coffee

If you would like to thank me and think I deserve a coffee, fee fry to by me one. Thanks a lot!
<a href="https://www.buymeacoffee.com/HelmerNL" target="_blank"><img src="https://cdn.buymeacoffee.com/buttons/v2/default-yellow.png" alt="Buy Me A Coffee" height="41" width="174"></a>