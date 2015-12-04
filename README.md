# Mosquitto Ansible Role

Installs and configures Mosquitto MQTT Broker.

# Configuration Options

Name                                   | Description
---------------------------------------|------------------------------------------------------------------------------
mosquitto_logging.connection_messages  | Log when clients connect and/or disconnect
mosquitto_logging.destination          | Log message destination
mosquitto_persistence                  | Write connection, subscription and message data to the disk
mosquitto_persistent_client_expiration | Remove persistent clients if they do not reconnect within a certain time frame

# Usage example

```yaml
---
- hosts: all
  sudo: true
  roles:
    - role: mosquitto
      mosquitto_persistent_client_expiration: 1d
      mosquitto_persistence:
        autosave_interval: 1000
      mosquitto_logging:
        destination: file /var/log/mosquitto/mosquitto.log
        connection_messages: true
```

# License

[![GPLv3](http://www.gnu.org/graphics/gplv3-127x51.png)](http://www.gnu.org/licenses/gpl-3.0.html)
