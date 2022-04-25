---
title: "Emissions from Use"
slug: "emissions-from-use"
description: "Analyzing the energy required to use a FarmBot and the associated footprint"
---

# Lesson overview

Every electrical component in FarmBot uses electricity to function: the motors, the solenoid valve, the Raspberry Pi computer, etc. In this lesson students will learn about the various electrical components in FarmBot and experimentally determine how much power each component uses. They will then calculate the energy, monetary, and CO2 footprint costs of operating FarmBot for a year.

|**Grades**   |6-10
|**Time**     |1.5 hours
|**Resources**|[Experiment](#experiment)
|**Standards**|{% include standard.html org="NGSS" code="3-5-ETS1-1" %}

# Experiment

Ask students to think about all of the components in the FarmBot that use electricity: the motors, LED lights, the Raspberry Pi computer, etc. Prompt the students with some leading questions:

- _What components within the FarmBot likely use the most or the least power?_
- _What uses more power: a FarmBot, a toaster, or a charging cell phone?_
- _How much energy would be required to run the FarmBot for a year?_
- _What is the carbon footprint impact of using a FarmBot for a year?_

Write the following table on the whiteboard and have students write it on a sheet of paper as well. Then call on students to list off different electrical components, adding each one to a new row on the left-side column.

|**Component**            |**Power (Watts)**|**Duty Cycle (%)**|**Use in 1 Day (Hours)**|**kWh/day**|**kWh/year**|**kg CO2/day**|**kg of CO2/year**
|Raspberry Pi             |
|Farmduino microcontroller|
|Electronics Box LEDs     |
|Motors                   |
|LED light strip          |
|Solenoid valve           |
|Vacuum pump              |

In this table students will record the **power in watts** that each electrical component of the FarmBot uses. We'll then calculate the amount of energy used by each component over a year, and the associated CO2 emmissions.

Explain the table headers:

- **Power (Watts):** The rate at which energy is generated or consumed. It is measured in units that represent energy per unit time, such as watts.
- **Duty Cycle (%):** The estimated percentage of time that a machine or device is operated, usually expressed as a percentage.
- **Use in 1 Day (Hours):** The total amount of hours in a day we expect to use a component of the FarmBot, based on the duty cycle.
- **kWh/day** and **kWh/year:** The total amount of energy used by a component (kWh) per day or per year.
- **kg CO2/day** and **kg of CO2/year:** The total amount of associated carbon emissions (kg CO2) emitted per day or per year.

## Measuring baseline power

{%
include callout.html
type="power-off"
title="Shutdown FarmBot"
content="If the FarmBot is not already turned off, use the web app to send a [shutdown command](https://my.farm.bot/app/designer/settings?highlight=shutdown_farmbot). Then unplug the FarmBot's power supply from the wall outlet."
%}

Plug the **kill-a-watt** power meter into the wall outlet and then plug the FarmBot into the kill-a-watt. This will allow students to measure exactly how much power the FarmBot is using.

Once FarmBot is plugged back in and powered on, some components will immediately begin using electricity while other components do not draw any power yet. Without moving any motors or operating any peripherals, ask the students which components are using electricity. Once students identify these components (the Raspberry Pi, the Farmduino microcontroller, and the electronics box LEDs), let them know that they'll be taking one power measurement for all three of these components grouped together. We'll call this the **baseline power** - the amount of power the FarmBot will use just be being plugged in.

Have students look at the kill-a-watt meter and record the amount of power the FarmBot is using in watts. Remember, this baseline power accounts for the Rpasberry Pi, the Farmduino microcontroller, and the Electronics Box LEDs. Because these components will use power no matter what when the FarmBot is powered up, the duty cycle should be 100%. From the duty cycle of 100%, we know that within a 24 hour period, these components will be powered up for all 24 hours.

|**Component**            |**Power (Watts)**|**Duty Cycle (%)**|**Use in 1 Day (Hours)**|**kWh/day**|**kWh/year**|**kg CO2/day**|**kg of CO2/year**
|Raspberry Pi             |
|Farmduino microcontroller|10 (baseline)    |100%              |24
|Electronics Box LEDs     |
|Motors                   |
|LED light strip          |
|Solenoid valve           |
|Vacuum pump              |

Using the measured power in watts and the number of hours the components are used in a day, we can calculate the kWh/day of energy usage with the following formula:

```
kWh/day = Power (watts) x Use in 1 Day (hours/day) / 1,000 (watts/kilowatts)
kWh/day = 10 x 24 / 1,000
kWh/day = 0.24

kWh/year = kWh/day x 365
kWh/year = 0.24 x 365
kWh/year = 87.6
```

|**Component**            |**Power (Watts)**|**Duty Cycle (%)**|**Use in 1 Day (Hours)**|**kWh/day**|**kWh/year**|**kg CO2/day**|**kg of CO2/year**
|Raspberry Pi             |
|Farmduino microcontroller|10 (baseline)|100%          |24                  |0.24   |87.6
|Electronics Box LEDs     |
|Motors                   |
|LED light strip          |
|Solenoid valve           |
|Vacuum pump              |

Because we don’t know how a specific consumer’s electricity is produced (coal vs solar vs whatever) we’re going to use the US average for CO2 emissions per kWh of electricity: 0.554 kg CO2/kWh. Have students calculate the C02 emissions associated with each component.

## Results analysis

Using thee estimations, students should find that operating a FarmBot will emit approximately 60kg of CO2/year, or 130lbs. As points of reference, this is equivalent to burning 6.5 gallons of gasoline in your car, and the energy used each day by FarmBot is close to what a desktop computer would use in about an hour and a half. Fun fact: at the average US electricity cost of $0.15/kWh, so operating FarmBot for a year will cost about $16.
