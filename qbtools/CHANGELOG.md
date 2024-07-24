## 3.1.2 - 2024-07-21

- added support for qbtools addons for hassio, ha operating system and ha supervisor users
- moved Qbus location based Overview form HAparms user to default.

## 3.1.1.2 - 2024-07-02

- support Qbus stepper

## 3.0.1   

- Expand @variable search to qbus properties in combination with HA entities
        E.G.
        Add codeblock below to HAparms
        - to format the Overview per qbus location
        - to format the Overview of settings>Devices and Service>Mqtt click on xx Devices button
        "ha":
            {
                "regexPost": [
                // ***************
                // codeblock start
                // ***************
                {
                    "name_regex": ".*",
                    "attributes":
                        { "device.identifiers": "[@location]",
                        "device.name": "[@location]",
                        "device.manufacturer": "QBUS",
                        "device.model": "Qbus"
                        }
                }
                // *************
                // codeblock end
                //**************
                ]
            }
- Correct defect in stopping influxdb interface when not all docker-compose env variables are defined