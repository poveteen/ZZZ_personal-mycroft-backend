# Mycroft Backend

[![Donate with Bitcoin](https://en.cryptobadges.io/badge/micro/1QJNhKM8tVv62XSUrST2vnaMXh5ADSyYP8)](https://en.cryptobadges.io/donate/1QJNhKM8tVv62XSUrST2vnaMXh5ADSyYP8)
[![Donate](https://img.shields.io/badge/Donate-PayPal-green.svg)](https://paypal.me/jarbasai)
<span class="badge-patreon"><a href="https://www.patreon.com/jarbasAI" title="Donate to this project using Patreon"><img src="https://img.shields.io/badge/patreon-donate-yellow.svg" alt="Patreon donate button" /></a></span>
[![Say Thanks!](https://img.shields.io/badge/Say%20Thanks-!-1EAEDB.svg)](https://saythanks.io/to/JarbasAl)

Personal mycroft backend alternative to mycroft.home, written in flask

Development moved to [MycroftAI Repo](https://github.com/MycroftAI/personal-backend)

please do not open issues or make PRs

# CONSIDER THIS ARCHIVED FOR HISTORICAL PURPOSES

![](personal_mycroft_backend/media/personalbackend.jpg)


## Install

from source

    git clone https://github.com/JarbasAl/personal-mycroft-backend
    cd personal-mycroft-backend
    pip install .

from pip

    pip install personal-mycroft-backend
    
configure backend by editing/creating ~/.mycroft/personal_backend/personal_backend.conf

    {
    "backend_port": 6712,
    "website_port": 5000,
    "ssl": true,
    "ssl_key": "/home/user/.mycroft/personal_backend/certs/MycroftPersonalServer.key",
    "ssl_cert": "/home/user/.mycroft/personal_backend/certs/MycroftPersonalServer.crt",
    "mail_port": 465,
    "mail_server": "smtp.googlemail.com",
    "mail_user": "xxx@gmail.com",
    "mail_password": "xxx",
    "secret_key": "MY_PRECIOUS_SECRET_KEY",
    "salt": "MY_TABLE_SALT"
    }

change url in "server" section in your default mycroft config

     // Address of the REMOTE server
      // Override: none
      "server": {
        "url": "https://0.0.0.0:6712",
        "version": "v0.1",
        "update": true,
        "metrics": true
      },



## usage

start backend 

    from personal_mycroft_backend.backend import start_backend
    
    start_backend()

start frontend

    from personal_mycroft_backend.frontend import start_frontend
    
    start_frontend()
    
more examples [here](https://github.com/JarbasAl/personal-mycroft-backend/tree/master/examples)

## Features / Routes


- get location

- geoip location default

- get config

- get device settings

- patch device settings

- pairing process

- send mail

- multiple STT engines supported (google, wit, ibm, kaldi, bing, houndify, govivace, deepspeech)

- sql database

- user email confirmation

- local browserless GUI if running on same machine

- website (status: WIP)

- store metrics (WIP - integrating into frontend, sql db and api endpoints functional)


# TODOS

- most of the frontend, are you a web dev? team up with me!

- STT json settings in db (for google cloud stt engine)

- skill settings

- wakeword upload

- wolfram alpha api

- weather api

- local data storage (audio recordings)

- if opt in proxy data to mycroft (utterances/hotwords/metrics)

- everything else i forgot

- new functionality
    - mimic 1 remote TTS 
    - user voice print from uploaded utterances / wakewords
    - train precise/snowboy models
