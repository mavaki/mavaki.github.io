---
layout: post
title: third-party development boards in Arduino IDE
date: 2024-06-21 21:25:00-0000
description: a hassel-free guide for setting up Arduino alternatives
tags: linux, research
categories: arduino
giscus_comments: true
related_posts: false
---

<style>
#boards {
  border-collapse: collapse;
  width: 100%;
}
#boards td, #boards th {
    border: 1px;
    text-align: left;
    padding: 8px;
}
/* #boards tr:nth-child(even){background-color: #f2f2f2;} */
/* #boards tr:hover {background-color: #ddd;} */
#boards th {
  padding-top: 12px;
  padding-bottom: 12px;
  text-align: left;
  background-color: #676767;
  color: white;
}
</style>

Getting started with Arduino IDE as a newbie is relatively straightforward, but it can be difficult when you're dealing with third-party boards that don't work out of the box. While I managed to get most of my devices working, an `Adafruit Bluefruit` kept throwing this error at me:

> A fatal error occurred: Failed to connect to ESP32: No serial data received.

Since it was challenging to find useful resources, I decided to write this blog post about the topic. I'm going to explain how to set up some common thiry-party boards in Arduino IDE using Linux, but the same process should apply for similar boards and different operating systems.

<br>
<table id="boards">
  <tr>
    <th>Board</th>
    <th>Package</th>
    <th>URL</th>
  </tr>
  <tr>
    <td><a href="https://www.keyestudio.com/products/keyestudio-esp32-plus-development-board-woroom-32-module-wifibluetooth-compatible-with-arduino">Keyestudio ESP32 PLUS Development Board</a></td>
    <td>esp32 by Espressif Systems</td>
    <td>https://dl.espressif.com/dl/package_esp32_index.json</td>
  </tr>
  <tr>
    <td><a href="https://www.seeedstudio.com/Seeed-XIAO-ESP32C3-p-5431.html">Seeed Studio XIAO ESP32C3</a></td>
    <td>esp32 by Espressif Systems</td>
    <td>https://files.seeedstudio.com/arduino/package_seeeduino_boards_index.json</td>
  </tr>
  <tr>
    <td><a href="https://www.adafruit.com/product/2821">Adafruit Feather HUZZAH with ESP8266</a></td>
    <td>esp8266 by ESP8266 Community</td>
    <td>http://arduino.esp8266.com/stable/package_esp8266com_index.json</td>
  </tr>
  <tr>
    <td><a href="https://www.digikey.ie/en/products/detail/adafruit-industries-llc/3406/7034992">Adafruit Feather nRF52 Bluefruit LE</a></td>
    <td>Adafruit nRF52 by Adafruit</td>
    <td>https://adafruit.github.io/arduino-board-index/package_adafruit_index.json</td>
  </tr>
</table>
<br>

In the `Board` column you will find the name of each board hyperlinked to the manufacturer's site. (Note that this is not the same URL that is included in the `URL` column.) Once you have identified your board, you will need to open Arduino IDE and navigate to the `Boards Manager` (`Tools` > `Board` > `Boards Manager`). Then you can search for the appropriate package (listed in the `Package` column) for your board. Click `Install` and wait until the installation is complete. Finally, copy the corresponding URL from the `URL` column and open the `Preferences` menu (`File` > `Preferences`), where you can paste the URL under `Additional boards manager URLs`. (This is a platform index URL that allows users to install and update platforms that are not included in the official package list.) Now you should be all set to select your device and begin programming, which I describe below.

If you're working with an original nRF52832 device like the `Adafruit Feather nRF52 Bluefruit LE`, you will likely need to update the bootloader. If you're using <i>Linux</i>, you will first need to install the `adafruit-nrfutil` package. The <a href="https://aur.archlinux.org/packages/python-adafruit-nrfutil">python-adafruit-nrfutil</a> package on the AUR worked for me, but there are also instructions on <a href="https://aur.archlinux.org/packages/python-adafruit-nrfutil">Adafruit</a> for other distributions. I was then able to select `Tools` > `Burn Bootloader`, which flashed my `Adafruit nRF52` and got everything running smoothly. If you experience any issues, you can refer to <a href="https://learn.adafruit.com/bluefruit-nrf52-feather-learning-guide/updating-the-bootloader">Adafruit</a>.

<br>
<table id="boards">
  <tr>
    <th>Group</th>
    <th>Entry</th>
    <th>Port</th>
  </tr>
  <tr>
    <td>esp32</td>
    <td>ESP32-WROOM-DA Module</td>
    <td>/dev/ttyUSB0</td>
  </tr>
  <tr>
    <td>esp32</td>
    <td>XIAO_ESP32C3</td>
    <td>/dev/ttyACM0</td>
  </tr>
  <tr>
    <td>esp8266</td>
    <td>Adafruit Feather HUZZAH ESP8266</td>
    <td>/dev/ttyUSB0</td>
  </tr>
  <tr>
    <td>Adafruit nRF52</td>
    <td>Adafruit Feather nRF52832</td>
    <td>/dev/ttyUSB0</td>
  </tr>
</table>
<br>

This table lists the information that you will need to select your board in Arduino IDE, and I've also included the port that I used (although yours might be different). Open `Tools` and hover over the `Board` option, where you will see the different packages that you have installed. Then refer to the `Group` and `Entry` columns to select your board. If your device is plugged in, the port should have been selected automatically, but you can also select it manually under `Tools` > `Port`.

At this point, you should be all set to get your board blinking ;) If you have any questions, feel free to leave a comment below.
