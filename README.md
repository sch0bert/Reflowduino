# Reflowduino - Modified by @sch0bert

## Introduction
I want to thank @botletics for his initial contribution. I took his project as a thing to do while I had COVID and I needed to keep myself busy with something for 2 weeks. As I always wanted to build my own reflow oven, I decided to explore some of the projects that were at www.instructables.com and took the one where I had quicker access to the materials in Mexico. 

The BOM I used is the next one:

- [Black and Decker TO3210SSD](https://a.co/d/aDQhKxE): I choose this oven as it has convection heating (up and down heaters) with a fan that I wanted to make use to cold down at the end of the reflow process.
- [ESP32 dev board](https://articulo.mercadolibre.com.mx/MLM-923211451-esp32-wifi-bluetooth-30pins-_JM)
- [Solid state relay SSR-25DA 25A with DC control input range 3-32 Vdc.](https://articulo.mercadolibre.com.mx/MLM-709007581-modulo-ssr-25da-relevador-de-estado-solido-25a-relay-3-32vdc-_JM)
- [MOSFET IRF520 module board but you can use any transistor to trigger the G3MB-202P relay (as is 5V input)](https://articulo.mercadolibre.com.mx/MLM-714880626-modulo-controlador-mosfet-irf520-arduino-raspberry-_JM)
- [Solid state relay G3MB-202P to control the AC fan](https://articulo.mercadolibre.com.mx/MLM-660400353-modulo-relevador-relay-estado-solido-ss-1-canal-2a-arduino-_JM)
- [Hi-Link AC to DC Regulator](https://articulo.mercadolibre.com.mx/MLM-1415321930-convertidor-ac-dc-fuente-de-5w-hlk-5m05-salida-5v-a-1a-_JM)
- [Fiberglass themal insulation](https://articulo.mercadolibre.com.mx/MLM-696533736-aislante-termico-acustico-de-fibra-de-vidrio-122-m-x-100-m-_JM)
- [MAX6675 module temperature sensor type K](https://articulo.mercadolibre.com.mx/MLM-816037002-termopar-tipo-k-sensor-temperatura-modulo-max6675-_JM)

I made some adjustments to the original code so you are free to compare them. Basically the modifications I made were:

- Add the MAX6675 as the temperature sensor.
- Add the control to trigger the fan once the reflow process is done.
- Adjusted the PID a little bit as I noticed the heater was not linear to the temperature sensor readings. When the temperature sensor reached 170 C, the PCB I was soldering reached the reflow level instead of the theoretical 220 C (generally).

Sorry for not having a complete documentation with all the steps I made, I felt that I was going to repeat what @botletics made originally. You can see some of the pictures of the final results. But hey! In case you have questions, ping me through my twitter @sch0bert I will be happy to help.

## The App

When I took the apk that was in the original repo, I never managed to get to connect to the device and it was giving me error so I decided to check the implementation through the mit app inventor web page. What I found was:

- The Bluetooth library that was originally used was already deprecated. I upgraded it to the latest one.
- Added an alarm when the reflow process was done.
- Here and there bug fixes.

The aia and apk files that are in this repo are the ones I upgrade.

## Overview
The Reflowduino project is an entire do-it-yourself (DIY) reflow ecosystem consisting of open-source hardware specifically built to make it easy to control reflow appliances and apply PID temperature control while maintaining full flexibility in programming and usage while offering a bunch of features.

## Safety Disclaimer
If you are a beginner in electronics or don't have the proper experience to work with mains voltage, I would suggest that you either don't mess with it, consult a professional, or keep learning until you're proficient enough! I am not liable for any mishaps that may occur due to misuse of the Reflowduino or its associated components or electrical system (including mains power). Take all safety precautions as necessary, such as gloves and certified safety glasses. Moreover, it is not recommended that you use the same appliance to reflow PCB's and also to cook food for consumption, which may result in food poisoning, especially with leaded solder. You are fully responsible for your actions, and perform them at your own risk!

That being said, DIY away my friends... have fun and stay safe!
