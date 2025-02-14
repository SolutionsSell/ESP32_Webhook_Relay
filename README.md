# ESP32_Webhook_Relay
Trigger a relay based off a webhook that is received by the ESP32

This project's goal is about triggering a relay based off of Verkada Webhooks. There are plenty of different ways to do this but Mehul and I have decided to use an ESP32 as our main hardware that is needed for this project.

The steps to achieving this goal are we need to have a publicly accessible web server that can ingest webhooks. Based off these webhooks, we need to filter out for a specific event and then trigger a relay on the ESP32 if we find the event we are looking for. 

Example, Verkada panic button is pressed which sends a webhook event to the server. We ingest that and flip a relay that is connected to a 3rd party notification system. The 3rd party notification system is then triggered to send mass notifications across a school to let everyone know there is an emergency.

Here is a link to the ESP32 that we used: https://www.amazon.com/dp/B08D5ZD528?ref=ppx_yo2ov_dt_b_fed_asin_title

----------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Steps taken to achieve goal:

Part 1: Run the web server on the ESP32

First you must install a couple of things.

Thonny IDE: https://thonny.org/

Micropython for ESP32-WROOM: https://micropython.org/download/ESP32_GENERIC/

ESP32 COM driver for windows (windows only): https://www.silabs.com/developer-tools/usb-to-uart-bridge-vcp-drivers?tab=downloads

Another install link is Micropython for the ESP32: https://micropython.org/download/ESP32_GENERIC/

Reference this video here for the rest of the Micropython ESP32 setup: https://www.youtube.com/watch?v=qoogOzSM0cM&ab_channel=ElectronicClinic

Once we have everything set up, we need to then run the code in the web_server file and continue to part 2.







Part 2: Publicly Accessible Web server on the ESP32

To achieve this part of the project, Mehul has found a way to use NGROK to make our server publicly accessible. There are other ways to this as well but NGROK is the easiest due to our networking situation.

NGROK cannot run directly on the ESP32 due to resource constraints. What needs to happen is running NGROK on a local machine but point all of the traffic to the ESP32's IP Address.

Create an account and install NGROK here on your local machine here: https://ngrok.com/downloads

Once installed, open up your terminal of choice and run the command:
ngrok http <esp32's IP>:80

You will then receive a link that is generated to send the webhooks to. Example: https://4d1a-27-132-122-204.ngrok-free.app




