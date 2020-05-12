# Updating Your Firmware

## Step 1 — Updating Your Firmware 


 * First disconnect and close the BoXZY interface. Then go to the link below and save the Firmware file: [Files](https://github.com/repetier/Repetier-Firmware)
 * Open Arduino and open the Firmware folder, click on the .INO file with the same name as the folder
 * Verify you've pulled multiple files into the interface, you should see many tabs.

## Step 2 


 * Under "Tools" under "Board" select the Mega 2560 Option. Click on it even if it's already selected.
 * Still in "Tools" go to "Processor" and select the Mega 2560 Option. Click on it even if it's already selected.
 * Once again, in "Tools" go to "Programmer" and select the Programmer "AVRISP MkII".

## Step 3


 * Verify no other USB ports are being used at this time. Make sure BoXZY's USB is plugged in but BoXZY is powered off.
 * MAIN POWER MUST BE OFF OR DISCONNECTED, but BoXZY must be plugged into the USB.
 * Go to "Tools" and under "Port" select the COM port your BoXZY uses, you must click on it even if it's already highlighted (It will show up with a different number than mine).
 * Click the green arrow in the upper left hand corner of the screen.
 * Once complete, if you have done it correctly, you will see some text at the bottom that says "done uploading". You can close the software at this point. You are done. If you get an error, repeat the steps and try again.
