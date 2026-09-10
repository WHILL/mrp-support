# Cannot power on

**English** · [日本語](power.md)

A decision flowchart for the most frequent enquiry we receive: the WHILL does not power on over the
serial interface. Please work through it before opening an issue.

Applies to Model CR2, Wheeled Robot Base, Electrical System Kit and Omni Platform.


## Flowchart

```mermaid
flowchart TD
    S(["Cannot power on<br>over the serial interface"]) --> Q1{"Does the power button<br>turn it on?"}

    Q1 -->|Yes| A1["Remove the battery, wait<br>20 minutes, then install<br>a charged battery"]
    Q1 -->|No| A5["Reseat the battery<br>Check for a loose fit<br>or a foreign object"]

    A1 --> Q2{"Does power-on over<br>the serial interface<br>work now?"}
    Q2 -->|Yes| R1(["Resolved<br>Was in deep sleep"])
    Q2 -->|No| Q3{"Does the<br>WHILL Serial API Tester<br>work?"}

    Q3 -->|Works| C2("Command not issued<br>correctly")
    Q3 -->|Does not work| C3("Bad connection<br>Communication module /<br>4-way cable /<br>D-sub cable")
    C2 --> A2["Send SetPower ON twice<br>Use an SDK"]
    C3 --> A3["Check for a<br>disconnected connector"]
    A3 -->|Still not fixed| M1(["Contact WHILL<br>mrp.contact@whill.inc"])

    A5 --> Q6{"Does it power on now?"}
    Q6 -->|Yes| R2(["Resolved<br>Battery was not seated"])
    Q6 -->|No| A6["Remove the battery and<br>connect it to the charger"]

    A6 --> Q4{"Is the charger<br>indicator normal?"}
    Q4 -->|Off, or keeps blinking red| C6("Charger failure")
    C6 --> M2(["Contact WHILL<br>mrp.contact@whill.inc"])
    Q4 -->|Normal| Q5{"Is the battery LED<br>normal?"}

    Q5 -->|Blinks blue| C5("Battery failure<br>over-discharge")
    C5 --> M3(["Contact WHILL<br>mrp.contact@whill.inc"])
    Q5 -->|Normal| C4("Bad connection<br>Battery /<br>magnet connector /<br>main controller")
    C4 --> A4["Re-seat the seat<br>Check for a<br>disconnected connector"]
    A4 -->|Still not fixed| M4(["Contact WHILL<br>mrp.contact@whill.inc"])

    classDef check fill:#f8f9fa,stroke:#495057,color:#212529
    classDef step fill:#cfe2ff,stroke:#0d6efd,color:#062c65
    classDef cause fill:#fff3cd,stroke:#d39e00,color:#3d2f00
    classDef solved fill:#d1e7dd,stroke:#0f5132,color:#0b2e21
    classDef contact fill:#f8d7da,stroke:#842029,color:#4d1319
    class S,Q1,Q2,Q3,Q4,Q5,Q6 check
    class A1,A3,A4,A5,A6 step
    class C2,C3,C4,C5,C6 cause
    class R1,R2,A2 solved
    class M1,M2,M3,M4 contact
```


**How to read this chart** — ◇ check　／　<b>blue</b> do this　／　<b>yellow</b> cause　／　<b>green</b> resolved　／　<b>red</b> contact WHILL

> **About deep sleep**
> Units shipped in certain periods enter deep sleep once the battery level reaches 19% or below.
> Such a unit does not answer on the serial interface and does not recover until the battery has
> been removed long enough to discharge it. The power button still turns the unit on, so the fault
> shows up as communication alone failing. It is most often seen on units left unused for a long time.

> **About the WHILL Serial API Tester**
> Model CR2 / Wheeled Robot Base / Electrical System Kit — https://whill.github.io/whill-serial-api/cr2/tester/
> Omni Platform — https://whill.github.io/whill-serial-api/omni/tester/
>
> It talks to the WHILL directly from Chrome or Edge. No installation and no driver, and it tells
> you at once whether the problem is in the WHILL or in your own program.


## Indicator locations

<img src="../../images/battery_charger_indicator_en.png" width="320" alt="Battery LED and charger indicator locations">

The **battery LED** is on the battery itself; the **charger indicator** is on the charger.


## Charger indicator

The lamp on the **charger**.

| Indication | Meaning |
|---|---|
| Blinking green | Charging |
| Solid green | Charge complete |
| Solid red | Standby — plugged into the wall outlet but not connected to the battery |
| Blinking red | Charge error |
| Off | No power reaching the charger |

> **Blinking red**
> The battery is not connected properly. Reconnect it. If it still blinks red, unplug the charger
> from the wall outlet, wait until the indicator goes out, then plug it in again. If several attempts do
> not clear it, the battery or the charger has failed.

> **Turns solid green immediately**
> If the indicator goes solid green while the battery is not fully charged, a different charger may
> be in use.


## Battery LED

The LED on the **battery**. Its colour shows the remaining charge.

| Colour | Remaining charge |
|---|---|
| Green | Full |
| Orange | About 30% to just under full |
| Red | Under about 30% |
| Purple | Empty |

**Abnormal indication**

| Indication | Meaning |
|---|---|
| Blinking blue | Battery failure, over-discharge. This is not a charge-level indication. |

> The battery LED goes out a while after charging completes. An LED that is off is not by itself a
> fault.


## Still not resolved

| Topic | Where |
|---|---|
| Serial communication, the specification, libraries | [Issues](https://github.com/WHILL/mrp-support/issues) |
| Repairs, replacement parts | mrp.contact@whill.inc |
