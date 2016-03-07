# Customizing jChat #
After getting the sources, jChat can be easily customized in different ways.

## Adding new tracks for mocked GPS location provider in jChat 1.1 ##
In jChat 1.1 the procedure for importing new tracks is changed, because the old mocked location provider is no more available.
jChat 1.1 provides a service that reads kml files in /data/misc/location and allows choosing which track to play and at which speed.
The new needed steps are:
  * Create a kml file with Google Earth as before (let's call the file track.kml). Please note that this time the file MUST end with .kml suffix

  * Run a shell on the emulator with _adb shell_ command, go to _/data/misc_ and create a folder name location with _mkdir location_

  * Exit from the adb shell

  * Copy the kml file to /data/location with: `adb push <PATH_TO_KML>\track.kml /data/misc/location`

  * Copy any other kml track to the same folder

  * Install the _MockedGPSLocationProvider.apk_ application with `adb install MockedGPSLocationProvider.apk`

  * Launch the _Mocked GPS Launcher_ application from the emulator

  * Select the desired kml file from the spinner

  * Choose the delay in milliseconds between the updates

  * Press _Start Service_ button

At this point Location updates for the provider named "gps" should have been started.

## Adding new tracks for mocked GPS location provider in jChat 1.0 ##
![http://jchat4android.googlecode.com/files/kml.jpg](http://jchat4android.googlecode.com/files/kml.jpg)

To add new tracks you should follow these steps:
  * Launch Google Earth

  * In the _Search_ tool, select the _Directions_ tab and specify the endpoints for your track

  * Right click on the _Route_ icon

  * Choose _Save place as_ and then _kml_ as file format

  * Rename your file to simply "kml" (no extension)

  * Launch Android emulator

  * Run a shell on the emulator with _adb shell_ command, go to _/data/misc/location_ and create a directory that shall have the same name of the Android location provider. You can choose whatever name you want (let's say "mygps"). To do so issue `mkdir /data/misc/location/mygps` command

  * Exit from the adb shell

  * Copy the kml file to the emulator issuing the command: `adb push <PATH_TO_KML> /data/misc/location/mygps`

  * Copy the location and properties files (that you can find in jchat sources under `cfg/locations` folder or under the `/data/misc/location/gps` folder on the emulator) in  `/data/misc/location/mygps`

  * Restart the Android emulator

  * Check the file strings.xml that you can find in `<JCHAT_ROOT>\res\values`. In particular you have to set the value of the `location_provider_name` variable like that `<string name="location_provider_name">mygps </string>`

  * Rebuild the `jChat apk` file with the new data

  * Install the  `jChat.apk` file on the emulator (with Eclipse or through `adb install`)

  * Launch jChat on the emulator
