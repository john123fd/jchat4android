# Getting started with jChat #

## Requirements ##
To be able to work with jChat you need the following:
  * [Google Android emulator](http://code.google.com/android/download.html)
  * A working installation of [JADE Leap](http://jade.tilab.com)
  * J2SE 1.5 or greater


## How to run jChat ##
To launch jChat follow these steps:
  * Download jChat apk file from the download area
  * Perform some customization if you wish
  * Launch Android emulator
  * Run the following command from the shell to install the application on the emulator:

```
      adb install <PATH_TO_APK>\jChat.apk 
```

  * Run the following command from the shell to start JADE main container:

```
      java -cp <PATH_TO_JADE_LEAP_JAR>\JadeLeap.jar -Djade_domain_df_autocleanup=true jade.Boot -gui  
```

  * Launch jChat application from Android emulator
  * Specify the host and port on which the JADE main container has been launched by choosing _MENU_ then _Jade Settings_
  * Choose _Connect to Jade!_ from jChat menu

For any further problem, please refer to [Android jChat User Guide](http://jchat4android.googlecode.com/files/Android%20jChat.doc)

If you need assistance, please post your questions on the JADE develop mailing list: [mailto://jade-develop@avalon.tilab.com](mailto://jade-develop@avalon.tilab.com)