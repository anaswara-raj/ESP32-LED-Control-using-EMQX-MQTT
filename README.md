# ESP32-LED-Control-using-EMQX-MQTT
Control an LED using ESP32 through EMQX Cloud with MQTT protocol for real-time IoT automation.

# ESP32 LED Control using EMQX MQTT

## Overview

This project controls an LED connected to an ESP32 using the MQTT protocol and EMQX Cloud broker.
The ESP32 connects to Wi-Fi and listens to an MQTT topic.
When a message is sent from an MQTT client, the LED turns ON or OFF.

---

## Components Required

* ESP32 Development Board
* LED
* 220Ω Resistor
* Breadboard
* Jumper Wires
* USB Cable
* Arduino IDE
* EMQX Cloud Account
* MQTT Client (MQTTX)

---

## Circuit Connections

| ESP32 Pin | Connection                         |
| --------- | ---------------------------------- |
| GPIO 2    | LED positive through 220Ω resistor |
| GND       | LED negative                       |

---

## MQTT Details

* Broker: EMQX Cloud
* Port: 1883
* Topic:

```text id="1l4x6t"
esp32/led
```

Messages:

```text id="0j5j1e"
ON   -> LED ON
OFF  -> LED OFF

## Libraries Used

```cpp id="jlwm3q"
#include <WiFi.h>
#include <PubSubClient.h>

## Setup Steps

### 1. Create EMQX Cloud Deployment

Create a Serverless deployment and copy:

* MQTT address
* Port
* Username
* Password

### 2. Update Code

```cpp id="ghxik0"
const char* ssid = "YOUR_WIFI_NAME";
const char* password = "YOUR_WIFI_PASSWORD";

const char* mqtt_server = "YOUR_BROKER_URL";
const int mqtt_port = 1883;
const char* mqtt_user = "YOUR_USERNAME";
const char* mqtt_pass = "YOUR_PASSWORD";

const char* topic = "esp32/led";
```

### 3. Upload Code

* Select **ESP32 Dev Module**
* Select correct COM port
* Click Upload

### 4. Test Project

Publish in MQTTX:

Topic:

```text id="d4p6ca"
esp32/led
```

Payload:

```text id="v97o91"
ON
```

Payload:

```text id="5j9u2n"
OFF
```

---

## Working

1. ESP32 connects to Wi-Fi
2. ESP32 connects to EMQX broker
3. ESP32 subscribes to topic
4. MQTT client sends ON/OFF message
5. ESP32 receives message
6. LED turns ON or OFF

---

## Applications

* Smart home automation
* Remote switching
* IoT learning projects

---

## Author

Anaswara Raj
