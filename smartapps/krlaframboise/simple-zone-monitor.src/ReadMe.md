**Simple Zone Monitor**

**Disclaimer:**  This is an Alpha Release so there are most likely some bugs and it's possible that future changes will break some of your settings and you'll have to reconfigure them.


----------


**Overview**

The Simple Zone Monitor allows you to monitor safety and/or security devices and perform Notifications (actions) when there's an issue.  

The ability to organize your devices using custom named **Zones and Zone Groups** is what makes this SmartApp unique.  

Zones should be used to group devices by their location, **NOT** by which devices should be armed together because the Device Exclusion feature allows you to ignore specific devices while a Zone is armed.

The original purpose of this SmartApp was to make it easier to specify track numbers for my Aeon Doorbell to play for groups of devices that are the same type and in a specific location.


----------


**Device Selection**

All devices are selected from one page and then the selected devices are displayed in consolidated lists throughout the rest of the SmartApp.


----------


**Monitoring Statuses**

The SmartApp uses "Monitoring Statuses" which are similiar to Modes and SHM statuses, but are specific to this SmartApp.  There are 10 available, but you can choose which ones will be available throughout the SmartApp. Examples: Armed (away), Armed (stay), Armed(sleep), ...

For each Monitoring Status you can configure:

* Arm/Disarm Triggers

* Delayed Entry/Exit and related Beep options

* Armed Zones

* Excluded Devices

* Safety Notifications

* Security Notification


----------


**Zones**

You can create custom named Zone Groups and Zones that provide a way to represent the information visually on a web dashboard, but the dashboard piece won't be available for a while.

For each zone you can:

* Choose Zone Group

* Choose Safety Devices (water, smoke, etc.)

* Choose Security Devices (door, window)

* Set Zone Message (uses tokens) for each type of device being monitored in the zone which can be used for Notifications.

The following is an example of how I recommend structuring your Zones:  

Living Room
* Zone Group: _First Floor_
* Security Devices: _LR Window 1, LR Window 2, LR Motion Sensor 1_

Laundry Room
* Zone Group: _Basement_
* Safety Devices: _Sump Pump Water Sensor_
* Security Devices: _Back Door, Laundry Room Motion Sensor_

Family Room
* Zone Group: _Basement_
* Security Devices: _Basement Window 1, Basement Window 2, Family Room Motion Sensor_
* Contact Sensor Zone Message: _A window in the family room has been opened_

_The zone message fields are optional, but they can be used for Notifications like TTS, Push, SMS and I use them to specify track numbers that get played by my Aeon Labs Doorbell.  There's a default Zone Message field in the Custom Message section that will be used when one isn't specified in the zone settings._


----------


**Arming/Disarming**

You can manually change the Monitoring Status through the main page of the SmartApp, but you can also setup triggers for each Monitoring Status.

These are the trigger options:

* SHM Status Changes

* Mode Changes

* CoRE Piston Change to True
_(after installng the SmartApp, you may need to open and close out of CoRe in order for the piston list to populate)_

* Switche Turns on or off

* Buttons #s are Held or Pressed

* Presence Changes to Present or Not Present (Options: First, Any, and All)


----------


**Advanced Settings**

* Choose Entry/Exit devices and the delay seconds for each Monitoring Status.

* Choose Confirmation beep devices and entry/exit beep devices with beep frequency for each Monitoring Status.  (Only devices with the "beep()" command will appear in the list)


----------


**Custom Messages**

You can setup an Event Message using tokens that can be used in Notifications.

You can setup a Default Zone Message using tokens that will be used in Notifications when a message wasn't specified in the Zone settings.



----------


**Notifications**

The notifications for Safety events and Security events are setup seperately and you can perform different actions for each Monitoring Status.  There's also an option that allows you to use the same settings for All Monitoring Statuses

These are the Notification Options you can use for each Monitoring Status:

* Add Zone Message or Event Message to Ask Alexa Message Queue

* Send Push with Zone Message or Event Message

* Add Zone Message or Event Message to Activity Feed

* Send SMS with Zone Message or Event Message

* Siren, Strobe, or Siren & Strobe (optionally specify turn off after)

* Turn on/off Switch (optionally specify level)

* Speak Zone Message

* Play Zone Message as Text (optionally set volume)

* Play Zone Message as Track (optionally set volume)

* Take Photo


----------


**Future Features**
_The details of these features will most likely changes as they're being implemented_

**Version 0.0.10** will have some options to help prevent false positives. 

These are some of the settings I'm considering:

* Zone Group option with choices like:
 - Any event (default)
 - Any event from more than one of its zones within x seconds.

 * Zone option with choices like: 
 - Not Set (default) _uses Zone Group setting_
 - Any event
 - Any 2 events within x seconds
 - Any contact sensor event or 2 motion sensor events within x seconds. 

**Version 0.0.11** will have a web dashboard that can be accessed from any browser.  This is one of the main reasons why zones should be setup based on device location.  

These are some of the features I'm thinking about:

* Main Page
 - Allows you to change the Monitoring Status
 - Possibly list all the activity and use icons to indicate the type of activity.
 - Possibly display the Zone Groups as boxes containing their name and icons indicating any activity and when clicked bring up a Zone Details page.
 - I'm considering adding an optional keypad feature you can enabled.  That dashboard could be used to prevent the Monitoring Status from being changed or maybe prevent all the pages from displaying anything until the code is entered.

* Zone Groups or Zone Group Details Page
 - Displays a box for each Zone Group unless only one is being displayed
 - Each box displays the Zone Group Name and has either a summary of the activity or a list of Zones(haven't decided yet).
 - If I decide to list the Zone Group's Zones, icons will be used to indicate Armed Status, Active Security Alerts, Pending Security Alerts, and Active Safety Alerts.
 - Clicking a Zone Group loads the Zones Page for that Zone Group.
 
* Zones Page
 - Displays a box for each Zone
 - Each box will display the Armed Status, Active Security Alerts, Pending Security Alerts, and Active Safety Alerts.
 - Each box might display a list of the Devices it's monitoring (I haven't decided yet).
 

