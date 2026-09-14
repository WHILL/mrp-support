<p align="center">
  <img src="images/whill_logo.svg" alt="WHILL" width="100">
</p>
<h1 align="center">
  WHILL Mobile Robot Platform — Technical Support
</h1>

<p align="center">
  <b>English</b> · <a href="README.md">日本語</a>
</p>

<p align="center">
  The technical support desk for the <b>WHILL Mobile Robot Platform (MRP)</b>, provided by WHILL, Inc.
</p>

<p align="center">
  <a href="docs/troubleshooting/power.en.md"><b>Cannot power on</b></a> ·
  <a href="https://github.com/WHILL/mrp-support/issues/new/choose"><b>Ask a question</b></a> ·
  <a href="https://whill-mrp.notion.site/WHILL-Mobile-Robot-Platform-97930066f5f64529bb83883aafef0c3b"><b>Product page</b></a>
</p>

<p align="center">
  <img width=22% title="WHILL Model CR2" src="images/model_cr2.png">
  <img width=24% title="Wheeled Robot Base" src="images/wheeled_robot_base.png">
  <img width=24% title="Omni Platform" src="images/omni_platform.png">
</p>

---

> [!TIP]
> **Cannot power on? Start here → [Cannot power on — flowchart](docs/troubleshooting/power.en.md)**

Technical questions about the MRP are welcome in this repository's [Issues](https://github.com/WHILL/mrp-support/issues).

Repairs and replacement parts are not a technical support topic — write to
**mrp.contact@whill.inc** instead.


## Common questions

Decision flowcharts for the problems we are asked about most. Please work through the relevant one
before opening an issue.

| Symptom | |
|---|---|
| **Cannot power on** (by the power button or over serial) | [Flowchart](docs/troubleshooting/power.en.md) |
| **Charger indicator does not light, or keeps blinking red** | [Flowchart](docs/troubleshooting/power.en.md) |
| **Battery LED blinks blue** | [Flowchart](docs/troubleshooting/power.en.md) |

For a communication problem, the [WHILL Serial API Tester](https://whill.github.io/whill-serial-api/cr2/tester/)
is the fastest first step — it talks to the WHILL directly from Chrome or Edge, so it tells you at
once whether the problem is in the WHILL or in your own program.


## WHILL Serial API

The serial communication interface of the MRP. Specification and browser-based tester:

### → **[https://whill.github.io/whill-serial-api/](https://whill.github.io/whill-serial-api/)**

| Product | Specification | Tester |
|---|---|---|
| **Model CR2**<br>Wheeled Robot Base<br>Electrical System Kit | [cr2/spec/](https://whill.github.io/whill-serial-api/cr2/spec/) | [cr2/tester/](https://whill.github.io/whill-serial-api/cr2/tester/) |
| **Omni Platform** | [omni/spec/](https://whill.github.io/whill-serial-api/omni/spec/) | [omni/tester/](https://whill.github.io/whill-serial-api/omni/tester/) |

The tester needs **Chrome or Edge**. It can be downloaded and used offline, and it communicates only
between your browser and the WHILL.


## Libraries

| Language | Library | Status |
|---|---|---|
| ROS 2 (Humble) | [ros2_whill](https://github.com/whill-labs/ros2_whill) | Supported |
| Python | [pywhill](https://github.com/WHILL/pywhill) | Supported |
| Arduino | [whill-sdk-arduino](https://github.com/WHILL/whill-sdk-arduino) | Supported |


## Archive

Support has ended for the items below. They are listed for reference only, because units and
installations remain in service.

| Item | Note |
|---|---|
| **WHILL Model CR** | Support has ended. Superseded by Model CR2. |
| [ros_whill](https://github.com/WHILL/ros_whill) (ROS 1 Melodic) | ROS 1 has reached end of life. Use [ros2_whill](https://github.com/whill-labs/ros2_whill). |
| [whill_control_system_protocol_specification](https://github.com/WHILL/whill_control_system_protocol_specification) | Superseded by the [WHILL Serial API](https://whill.github.io/whill-serial-api/). The PDFs cover Model CR and are no longer maintained. |
