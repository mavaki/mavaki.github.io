---
layout: post
title: third-party development boards in Arduino IDE
date: 2024-06-20 06:45:00-0000
description: a hassel-free guide for setting up Arduino alternatives
tags: linux, research
categories: arduino
giscus_comments: true
related_posts: false
---

Getting start with Arduino IDE as a newbie is relatively straightforward, but it becomes difficult when you're dealing with third-party boards that involve some extra steps. I'm going to explain how to set up the following boards in Arduino IDE using Arch Linux, but the same process should apply for similar boards/distributions.

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

<table id="boards">
  <tr>
    <th>Board Name</th>
    <th>Selected Board</th>
    <th>Arduino URL</th>
  </tr>
  <tr>
    <td><a href="https://www.keyestudio.com/products/keyestudio-esp32-plus-development-board-woroom-32-module-wifibluetooth-compatible-with-arduino">Keyestudio ESP32 PLUS Development Board</a></td>
    <td>ESP32-WROOM-DA Module</td>
    <td>https://dl.espressif.com/dl/package_esp32_index.json</td>
  </tr>
  <tr>
    <td><a href="https://www.adafruit.com/product/2821">Adafruit Feather HUZZAH with ESP8266</a></td>
    <td>Adafruit Feather HUZZAH ESP8266</td>
    <td>http://arduino.esp8266.com/stable/package_esp8266com_index.json</td>
  </tr>
  <tr>
    <td><a href="https://www.seeedstudio.com/Seeed-XIAO-ESP32C3-p-5431.html">Seeed Studio XIAO ESP32C3</a></td>
    <td>XIAO_ESP32C3</td>
    <td>https://files.seeedstudio.com/arduino/package_seeeduino_boards_index.json</td>
  </tr>
  <tr>
    <td><a href="https://www.digikey.ie/en/products/detail/adafruit-industries-llc/3406/7034992">Adafruit Feather nRF52 Bluefruit LE</a></td>
    <td>Adafruit Feather nRF52832</td>
    <td>https://adafruit.github.io/arduino-board-index/package_adafruit_index.json</td>
  </tr>
</table>


For each of the boards I'm using, I had to install...

`A fatal error occurred: Failed to connect to ESP32: No serial data received.`
