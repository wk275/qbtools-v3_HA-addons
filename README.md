# Home assistant addons
![](https://img.shields.io/badge/release-v3.1.2-blue)                 
![](https://img.shields.io/badge/arch-arm64-yellow)
![](https://img.shields.io/badge/-armv7-yellow) 
![](https://img.shields.io/badge/-amd64-yellow)
<br/>
![](https://img.shields.io/badge/interfaces_with-qbus_devices-green)
![](https://img.shields.io/badge/-home_assistant_devices-green)
![](https://img.shields.io/badge/-influxDB_v2/grafana_statistics-green)
![](https://img.shields.io/badge/-http_devices-green)
<br/>
![](https://img.shields.io/badge/prerequisites-HA--Operating_system-red)
![](https://img.shields.io/badge/-Hassio-red)
![](https://img.shields.io/badge/-HA--Supervised-red)

# Installation:
Install the 3 addons below. Preferred install priority is qbmos, qbtools, qbusmqtt.

[![Open your Home Assistant instance and show the add add-on repository dialog with a specific repository URL pre-filled.](https://my.home-assistant.io/badges/supervisor_add_addon_repository.svg)](https://my.home-assistant.io/redirect/supervisor_add_addon_repository/?repository_url=https://github.com/wk275/qbtools-v3_HA-addons.git)

## [qbmos](https://github.com/wk275/qbtools-v3_HA-addons/tree/main/qbmos)

Installs a mosquitto server for Qbtools. Change MQTT_USER and MQTT_password to your own preference in the config tab. 

#### After configuration and start of qbmos 
#### Copy following variables to addons qbtools and qbusmqtt

- the qbmos hostname -> MQTT_HOST variable
![alt text](<Qbmos hostname.png>)
- the credentials -> MQTT_USER and MQTT_PASSWORD

If you want to use your own MQTT server, do not istall this addon. In that case  change the MQTT_HOST, MQTT_PORT, MQTT_USER, MQTT_PASSWORD variables in both addons qbtools and qbusmqtt conform your setup.

## [qbtools](https://github.com/wk275/qbtools-v3_HA-addons/tree/main/qbtools)

Installs Qbtools HA sofware. This addon will create HA entities.
</br>Change the MQTT_HOST, MQTT_USER and MQTT_PASSWORD variables as described above.

## [qbusmqtt](https://github.com/wk275/qbtools-v3_HA-addons/tree/main/qbusmqtt)

Installs the QBUS MQTT gateway. 
<br/>Change the MQTT_HOST, MQTT_USER and MQTT_PASSWORD variables as described above.

## MQTT 
Don't forget to add the MQTT integration via 
</br> settings > devices & services >  push "+ ADD INTEGRATION" button > type MQTT 

If you already installed and started the addons before you enabled the MQTT service, the status of your qbus outputs will not be updated/available. There is, to my knowledge no way to detect this situation. So in this case you need to restart qbtools, qbusmqtt or homeassistant. After a restart of one of these services, the status should become available.

## HA_parms 
HAparms can still be used. For this you first need to install a ssh addon. 
</br>If you installed the "Advanced SSH & Web Terminal" addon don't forget to assign a password in the config tab before starting the addon.

After installation of the ssh addon, click on terminal in the sidebar. This should bring you to the linux directory /root.
Here, you'll find the HAparms_example.js file in a directory "addon_configs/?_qbtools".
Copy this example file to HAparms.js and modify it conform your needs. When saved it will modify the HA entities after a while. For details see log file in log tab of qbtools addon.

# Remarks

⚠️ wk275/qbtools, wk275/qbmos & wk275/qbusmqtt are not officially supported by Qbus.
