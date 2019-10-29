# Bluetooth-Car
Tiny car controlled using bluetooth on any android device.

## Components

* Arduino Nano
* Two DC gear motors
* Two robot wheels
* Chassis
* HC-05 Bluetooth Module
* Four (4) AA batteries and battery holder
* L293D/L298N Motor Driver IC

## Connections

HC-05 | Arduino
---|---
VCC | 5V
GND | GND
 Rx | Tx
Tx| Rx

![Connections](https://cdn.instructables.com/FTN/T5T3/INPE4663/FTNT5T3INPE4663.LARGE.jpg?auto=webp&width=1024&height=1024&fit=bounds)

## App making

1. Go to the web: [App Inventor](http://ai2.appinventor.mit.edu/) and log in with a gmail account.

2. Click Continue to dismiss the splash screen

3. Start a new project, give a name without any space

4. The Designer will open.

5. Add a Label, a ListPicker, 5 Buttons, a Slider and another Button.

6. Then add two Non-visible components (BluetoothClient1 & Notifier1)

![App01](https://cdn.instructables.com/FG5/DMT5/INOTZZ4W/FG5DMT5INOTZZ4W.LARGE.jpg)

![App02](https://cdn.instructables.com/FP0/EOQD/INOTZZUK/FP0EOQDINOTZZUK.LARGE.jpg)

7. Use 5 images for five buttons (4 arrows & 1 stop), you have to upload image in media section first to do that.

Our UI design is completed. Now, we have to define the behavior of UI component's from Block Editor.

8. App Initialization: The first step is to check that Bluetooth is activated or switched on. If not, an error message is displayed reminding the user to open Android’s Settings and then switch Bluetooth to on.

The Initialize event occurs when the app is launched – and this is a good place to check whether or not Bluetooth is enabled on the device.

![Code01](https://cdn.instructables.com/FR6/JHJU/INOU01UI/FR6JHJUINOU01UI.LARGE.jpg)

9. Connecting: When the device is running, the user selects the device name from a list of available Bluetooth devices. Because the list of devices is in the form of a list, the ListPicker is a great interface component to display the device list and handle the selection. Before the list is displayed, the list is filled with the list of Bluetooth devices (AddressesAndNames).

![Code02](https://cdn.instructables.com/FN0/J3C2/INPCS011/FN0J3C2INPCS011.LARGE.jpg)

After the device has been selected with the ListPicker user interface, the Connect method of BluetoothClient1 establishes the connection. The method returns a value of true if the connection was successful. If connection become successful then change the Label1 text to 'Status: Connected' in Green color.

![Code03](https://cdn.instructables.com/FC4/83KZ/INPCS0D7/FC483KZINPCS0D7.LARGE.jpg)

When disconnect button is click BluetoothClient1 become disconnected and Label1 text changed to Status: Not Connected in red color.

![Code04](https://cdn.instructables.com/FPE/W509/INPCS17K/FPEW509INPCS17K.LARGE.jpg)

When anyone from 5 control buttons (Up, Down, Left, Right & Stop) is clicked then it sends 1 byte unique number to the receiving device (HC-05 connected to Arduino).

![Code05](https://cdn.instructables.com/FKV/QEGP/INPCS1WQ/FKVQEGPINPCS1WQ.LARGE.jpg)

When slider position become changed it sent the current position to the receiver.

![Code06](https://cdn.instructables.com/FVC/16O7/INPCS2E0/FVC16O7INPCS2E0.LARGE.jpg)

Click to Build menu and select save apk to my computer. An apk file will be generated and downloaded to your computer. Transfer it to your mobile phone and install in your device.

## Links

[AIA code for App Inventor](https://cdn.instructables.com/ORIG/FEE/IAWO/INPCS447/FEEIAWOINPCS447.aia)

[APK ready by Taifur](https://cdn.instructables.com/ORIG/FWG/5LC6/INS17CKR/FWG5LC6INS17CKR.apk)
