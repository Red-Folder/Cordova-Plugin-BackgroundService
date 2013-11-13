# Background Service Plugin for Phonegap #

A plugin (and framework code) that allows the development and operation of an Android Background Service.

The example MyService Background Service will write a Hello message to the LogCat every minute.  The MyService is designed as sample code.

## Adding the plugin to your project ##

Copy the files to the following locations:

* libs\backgroundserviceplugin-3.1.0.jar
* src\com\yournamespace\yourappname\MyService.java
* assets\www\backgroundService-3.1.0.js
* assets\www\myService-3.1.0.js
* assets\www\index-3.1.0.html

Add the following to res\xml\config.xml

```
    <feature name="BackgroundServicePlugin">
      <param name="android-package" value="com.red_folder.phonegap.plugin.backgroundservice.BackgroundServicePlugin"/>
    </feature>
```

Add the following to AndroidManifest.xml

```
<uses-permission android:name="android.permission.RECEIVE_BOOT_COMPLETED" />

<!-- To be added within Application nde -->
<service android:name="com.yournamespace.yourappname.MyService">
	<intent-filter>         
		<action android:name="com.yournamespace.yourappname.MyService"/> 
	</intent-filter>     
</service>

<receiver android:name="com.red_folder.phonegap.plugin.backgroundservice.BootReceiver">
	<intent-filter>     
		<action android:name="android.intent.action.BOOT_COMPLETED"></action>   
	</intent-filter> 
</receiver>
```
## Change Log ##

* 9th November 2013 - Added ability to listen for doWork() updates using registerForUpdates/ deregisterForUpdates.  For more info see https://github.com/Red-Folder/Cordova-Plugin-BackgroundService/issues/17
* 20th September 2013 - Added runOnce support (see https://github.com/Red-Folder/Cordova-Plugin-BackgroundService/issues/14)
* 4th September 2013 - Fixes for NullPointerException (see https://github.com/Red-Folder/Cordova-Plugin-BackgroundService/issues/7)
* 27th August 2013 - Added TimerMilliseconds to returned JSONObject (see Issue 5)
* 12th May 2013 - Updated to handle service being restarted by OS
* 14th November 2012 - Fix for service not stopping if the app has been closed then re-opened

## Further Information ##

Further information on the plugin can be found at:

* http://red-folder.blogspot.co.uk/2012/09/phonegap-android-background-service.html
* http://red-folder.blogspot.com/2012/09/phonegap-android-background-service_11.html

The below is a tutorial to create your own Twitter service:

* http://red-folder.blogspot.com/2012/09/phonegap-service-tutorial-part-1.html
* http://red-folder.blogspot.com/2012/09/phonegap-service-tutorial-part-2.html
* http://red-folder.blogspot.com/2012/09/phonegap-service-tutorial-part-3.html

Please let me know your thoughts and comments.

## Spread the love ##

If you find the Background Service Plugin useful then spread the love.

All the work I do on the Plugin is done in my spare time - time I would otherwise be spending taking my wife out for a nice meal or helping my lad find vinyl records (he's currently very much into The Smiths, Fleetwood Mac and Kate Bush).

The Plugin is free and will always remain free.  I will continue to develop, maintain and distribute the Plugin under the MIT License.

https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=E64TCFQ3NLHZ8

## Licence ##

The MIT License

Copyright (c) 2013 Red Folder Consultancy Ltd

Permission is hereby granted, free of charge, to any person obtaining a copy of this software and associated documentation files (the "Software"), to deal in the Software without restriction, including without limitation the rights to use, copy, modify, merge, publish, distribute, sublicense, and/or sell copies of the Software, and to permit persons to whom the Software is furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE SOFTWARE.


