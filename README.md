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

## [qbmos](https://github.com/wk275/qbtools-v3_HA-addons/tree/main/qbmos)

Installs a mosquitto server for Qbtools on port 51883.
Change MQTT_USER and MQTT_password to your own preferences in the config tab. These credentials should be copied to the add-ons qbtools and qbusmqtt if qbmos is used.

If you want to use your own MQTT server do not istall this addon. In that case the MQTT_HOST, MQTT_PORT, MQTT_USER, MQTT_PASSWORD variables in both addons qbtools and qbusmqtt should be changed conform your setup.

## [qbusmqtt](https://github.com/wk275/qbtools-v3_HA-addons/tree/main/qbusmqtt)
Installs the QBUS MQTT gateway. Change the MQTT_USER and MQTT_PASSWORD variables in the config tab to the ones you used in the qbmos configuration. DO NOT CHANGE the MQTT_HOST and MQTT_PORT. The defaults should work. See tab log for details.

## [qbtools](https://github.com/wk275/qbtools-v3_HA-addons/tree/main/qbtools)
Installs Qbtools sofware. This will create the HA entities. Change the MQTT_USER and MQTT_PASSWORD variables in the config tab to the ones you used in the qbmos configuration. The MQTT_HOST name should be copied from the qbmos addon config page. Do not change the MQTT_PORT. The default should work. See tab log for details.

[![Open your Home Assistant instance and show the add add-on repository dialog with a specific repository URL pre-filled.](https://my.home-assistant.io/badges/supervisor_add_addon_repository.svg)](https://my.home-assistant.io/redirect/supervisor_add_addon_repository/?repository_url=https://github.com/wk275/qbtools-v3_HA-addons.git)


## MQTT 
Don't forget to add the MQTT integration via settings>devices é services> add integrtaion button>MQTT 

## HA_parms 
HAparms can still be used. For this you first need to install a ssh addon.

After installation  a click on terminal in the sidebar should bring you to the directory /root.
You'll find the HAparms_example.js file in directory "addon_configs/9fdccc3d_qbtools".
Copy it to HAparms.js and modify it conform your needs. When saved it will modify the HA entities after a while. For details see log file in log tab of qbtools addon.
