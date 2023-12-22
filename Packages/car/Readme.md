
# Charge Reminder

- Charge Reminder
    - [Calendar Integration](#calendar-integration)
    - [Sensor Templates](#sensor-template)
    - [Waze Travel Time Config](#waze-travel-time-config)
    - [Thanks](#thanks-and-contact)


## Calendar Integration

I assume for this script that you already have setup your calendar integration and fill out the *location* field when you create an appointment. Since the Waze integration does not understand all locations correctly, I had to add *Netherlands* to the sensor since I'm not usually adding my own country to an appointment address. But your result may differ off course. 

If you have questions, please contact me through social media and i'm happy to point you in the right direction.

## Sensor Template
If you have your calender configured, you can use the templates mentioned [here](/Packages/car/charging_reminder_sensor.yaml) to configure your location sensors. These sensors can be used in the Waze Travel Time configuration, so you can have a *flexible* destination and there is not need to manually create a new Waze Travel Time config for each new appointment.

## Waze Travel Time Config
Install the official [Waze Travel Time](https://www.home-assistant.io/integrations/waze_travel_time) integration and one location. Give it a name you like and use the following variables:
* Origin : **zone.home**
* Destination: **sensor.waze_event_destination**
* Region: **Europe**

![Waze Travel Time Config](/images/waze_travel_time01.png)

## Charge Reminder Script
You can use the script as-is for now. You can find the latest version [here](/Packages/car/charging_reminder.yaml).


## Thanks and contact

Feel free to contact me if you have any questions.
* [Threads](https://www.threads.net/@helmernl)
* [Twitter](https://twitter.com/helmernl)


## Buy me a Coffee

If you would like to thank me and think I deserve a coffee, fee fry to by me one. Thanks a lot!

<a href="https://www.buymeacoffee.com/HelmerNL" target="_blank"><img src="https://cdn.buymeacoffee.com/buttons/v2/default-yellow.png" alt="Buy Me A Coffee" height="41" width="174"></a>