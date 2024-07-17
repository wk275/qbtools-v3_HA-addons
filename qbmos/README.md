# qbmos is a customized mosquitto server. 

Instead of defining a user and password via the standard mosquitto tools, you can directly define them via the docker-compose.yaml environment variables MQTT_USER and MQTT_PASSWORD.

For details see <https://github.com/wk275/qbTools-v3>

docker-compose:

````
  qbmos:
    image: wk275/qbmos:latest
    environment:
      - TZ=Europe/Brussels
      - MQTT_USER=<define your mqtt username here>
      - MQTT_PASSWORD=<define your mqtt user password here>
    container_name: qbmos-v3
    restart: unless-stopped
    ports:
      - "1883:1883"
    volumes:
      - ./mosquitto/data:/mosquitto/data
````

# Remarks

⚠️ wk275/qbtools, wk275/qbmos & wk275/qbusmqtt are not officially supported by Qbus.
