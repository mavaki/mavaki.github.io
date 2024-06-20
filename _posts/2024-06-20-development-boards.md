---
layout: post
title: third-party development boards in Arduino
date: 2024-06-20 06:45:00-0000
description: a hassel-free guide for setting up Arduino alternatives
tags: linux, research
categories: arduino
giscus_comments: true
related_posts: false
---

`A fatal error occurred: Failed to connect to ESP32: No serial data received.`

Borderless Electronics -- Arduino Leonardo -- /dev/ttyACM0

<table style="width:100%">
  <tr>
    <th>Board Name</th>
    <th>Selected Board</th>
    <th>Selected Port</th>
    <th>Arduino URL</th>
  </tr>
  <tr>
    <td><a href="https://www.keyestudio.com/products/keyestudio-esp32-plus-development-board-woroom-32-module-wifibluetooth-compatible-with-arduino">Keyestudio ESP32 PLUS Development Board</a></td>
    <td>esp32 > ESP32-WROOM-DA Module</td>
    <td>/dev/ttyUSB0</td>
    <td>https://dl.espressif.com/dl/package_esp32_index.json</td>
  </tr>
  <tr>
    <td><a href="https://www.adafruit.com/product/2821">Adafruit Feather HUZZAH with ESP8266</a></td>
    <td>esp8266 > Adafruit Feather HUZZAH ESP8266</td>
    <td>/dev/ttyUSB0</td>
    <td>http://arduino.esp8266.com/stable/package_esp8266com_index.json</td>
  </tr>
  <tr>
    <td><a href="https://www.seeedstudio.com/Seeed-XIAO-ESP32C3-p-5431.html">Seeed Studio XIAO ESP32C3</a></td>
    <td>esp32 > XIAO_ESP32C3</td>
    <td>/dev/ttyACM0</td>
    <td>https://files.seeedstudio.com/arduino/package_seeeduino_boards_index.json</td>
  </tr>
  <tr>
    <td><a href="https://www.digikey.ie/en/products/detail/adafruit-industries-llc/3406/7034992">Adafruit Feather nRF52 Bluefruit LE</a></td>
    <td>Adafruit nRF52 > Adafruit Feather nRF52832</td>
    <td>/dev/ttyUSB0</td>
    <td>https://adafruit.github.io/arduino-board-index/package_adafruit_index.json</td>
  </tr>
</table>
