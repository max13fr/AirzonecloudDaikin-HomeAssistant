# Airzone Cloud Daikin plugin for Home Assistant

## Introduction

Allow to view & control all your zones register on your *Daikin* Airzone Cloud ([dkn.airzonecloud.com](https://dkn.airzonecloud.com)) account from [Home Assistant](https://www.home-assistant.io/).

If you're looking for the main Airzone Cloud ([airzonecloud.com](https://airzonecloud.com)), use this plugin : https://github.com/max13fr/Airzonecloud-HomeAssistant

![Screenshot](screenshot.png)

## Install / upgrade

### Add module

In your home assistant directory (where you have your **configuration.yaml**) :

- create the directory **custom_components** if not already existing
- copy **custom_components/airzoneclouddaikin** directory from this github repository inside your **custom_components**. In case of upgrade, you can delete the **airzoneclouddaikin** first then copy the new one.

Finally, you should have the following tree :

- configuration.yaml
- custom_components/
  - airzoneclouddaikin/
    - \_\_init\_\_.py
    - climate.py
    - const.py
    - manifest.py

### Configure

In your **configuration.yaml** add the following lines :

```
climate:
  - platform: airzoneclouddaikin
    username: your@mail.com
    password: yourpassword
```

You're username & password should match what you use to connect to https://dkn.airzonecloud.com

Don't forget to restart your Home Assistant when you update your configuration.

#### Change refresh interval

Default refresh interval is **10 seconds**.

You can increase or decrease this value but be warned that you can be banned by Airzone if you refresh too often.

```
climate:
  - platform: airzoneclouddaikin
    username: your@mail.com
    password: yourpassword
    scan_interval: 5
```
