# ESP32_Webhook_Relay
Trigger a relay based off a webhook that is received by the ESP32

This project's goal is about triggering a relay based off of Verkada Webhooks. There are plenty of different ways to do this but Mehul and I have decided to use an ESP32 as our main hardware that is needed for this project.

The steps to achieving this goal are we need to have a publicly accessible web server that can ingest webhooks. Based off these webhooks, we need to filter out for a specific event and then trigger a relay on the ESP32 if we find the event we are looking for. 

Example, Verkada panic button is pressed which sends a webhook event to the server. We ingest that and flip a relay that is connected to a 3rd party notification system. The 3rd party notification system is then triggered to send mass notifications across a school to let everyone know there is an emergency.

