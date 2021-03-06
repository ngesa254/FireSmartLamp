# FireSmartLamp
It's a Firebase showcase that shows how we can leverage Firebase as the backend of IoT device. 
In this case, I create a Smart Lamp using Raspberry Pi 2. Thanks to Firebase, it's controllable over the internet. 


All I have to do next is creating a web or mobile app, to change some values in Firebase database, 
and that change will be propagated to and processed by IoT device to do some actions.


I use this demo to talk about Firebase in 2 GDG DevFest events, in [Jakarta](https://sites.google.com/a/kibar.co.id/devfest-indonesia-2015/program/jakarta)
(Oct 17) and [Surabaya](https://sites.google.com/a/kibar.co.id/devfest-indonesia-2015/program/surabaya) (Oct 18).

The story behind this project is in [this deck](http://www.slideshare.net/andri_yadi/firebase-54159652)


##Background
My team in [DyCode](http://dycode.co.id) and I have been using Firebase since early 2014 in several products and projects. So, I know a bit about Firebase :)
Most of the Firebase usecases we did so far are for chat app and for data synchronization across related apps. 
Samples and talks around Firebase are around mobile and web apps, but I haven't see one that's related to IoT. 
As my recent passion is around IoT, why not creating Firebase usecase for IoT, right? :)


Granted, for IoT, especially the one that requires more low level programming like Arduino and other MCUs, 
there're already de-facto protocols and SDKs, such as: MQTT and CoAP. I just wanna do something different with IoT and Firebase.
As you can see in the code, it's super easy to get started (hey, I don't say MQTT is hard though). 
Your knowledge around Firebase is fully usable in this IoT scenario.


##Components

To properly deploy the project, you need to prepare following components:

* Raspberry Pi 2 with Raspbian OS. Node.js runtime should be installed.
* Solid state AC switch circuit (find the circuit [here](http://www.slideshare.net/andri_yadi/firebase-54159652/36?src=clipshare))
* AC light bulb
* AC current sensor ACS712 5A
* Analog to Digital Converter IC MCP3008
* Voltage divider circuit to convert 5 volts to 3.3 volts. Output from ACS712 is 5 volts, while Raspberry Pi expects 3.3 volts.
* Light-dependent Resistor (LDR) and a 10K resistor

The circuit involved in this project is explained [here](http://www.slideshare.net/andri_yadi/firebase-54159652/41?src=clipshare)


##Run the app
The app is written in Node.js and run in Raspberry Pi. For that, you need to install Node.js runtime in Raspberry Pi OS. 
Here I use Raspbian, but I guess you can use any Linux-based OS, as long as you are managed to install Node.js runtime in it.

Then, you need to have Firebase account. Sign up [here](http://firebase.com/signup/) if you haven't. 
Then create a new Firebase app and you'll get an URL, e.g: `http://my-iot.firebaseio.com`, where `my-iot` is your Firebase Project ID.

In `index.js` file, about line 58, change `[YOUR-OWN-FIREBASEAPP]` in `https://[YOUR-OWN-FIREBASEAPP].firebaseio.com` with your Firebase Project ID.

Finally, don't forget to run
```npm install```
to download and install all required Node.js modules.

That's it (if my memory serves me well :P). Found bugs or issues or have question? Create an issue or you can always contact me at contacts below.

Enjoy!


##Android app
I made a basic Android app for controlling this smart lamp. Now you can actually turn on/off the lamp from anywhere in the world :)

Get it here: [https://github.com/andriyadi/FireSmartLamp-Android](https://github.com/andriyadi/FireSmartLamp-Android)


##Contact me

Andri Yadi

* Email: an dot dri at me dot com
* Twitter: http://twitter.com/andri_yadi
* LinkedIn: https://www.linkedin.com/in/andriyadi

For professional services, you can contact my company: office at dycode dot com

##Using it
You're welcome to use it in your projects and make any changes. Just please keep the acknowledgement.

##License
Copyright (c) 2015 Andri Yadi

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.




