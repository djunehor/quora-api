Quora (Unofficial) API
=========
[![Build Status](https://travis-ci.org/djunehor/quora-api.svg?branch=master)](https://travis-ci.org/djunehor/quora-api) [![HitCount](http://hits.dwyl.io/djunehor/quora-api.svg)](http://hits.dwyl.io/djunehor/quora-api)
####Please open issues and make pull requests regarding this at [djunehor/quora-api](http://github.com/djunehor/quora-api).

An unofficial API for Quora.

PS: Please use responsibly and ensure you're not violating any nairaland rule.

### Table of Contents
* [API Usage](#api-usage)
* [Features](#features)
* [Installation](#installation)
* [Contributing](#contributing)

# API Usage
### API Base URL: `https://quorapy-api.herokuapp.com`

## Endpoints Summary
* POST: [`/search`](#api-search) {term: String, question_limit=Int, answer_limit=Int, load_user=Boolean}
 
### GET: `search`
#### api-search
Example usage: `GET http://<BASE_URL>/search`

Example result:
```json
{
  "answer_limit": 1,
  "data": [
    {
      "comments": [
        {
          "text": "Rather than giving you a boring step by step process of learning Python, I would share my personal journey about how I started learning Python.\nHere is my personal learning experience:\nWhat motivated me to start learn Python ?\nI fell in love with Python after reading a bunch of answers on Quora about how people were doing wonderful things with Python.\nSome were writing scripts to automate their Whats app messages.\nSome wrote a script to download their favourite songs,\nwhile some built a system to receive cricket score updates on their phones.\nAll of this seemed very excited to me and I finally dec...(more)",
          "user": {
            "datetime": "2019-09-29 02:52:30.692237",
            "name": "",
            "url": "https://www.quora.com/profile/Neha-Ahuja-178"
          }
        }
      ],
      "question": {
        "datetime": "2019-09-28 23:57:00",
        "text": "How should I start learning Python?",
        "user": {
          "name": "Quora Content Review",
          "url": "https://quora.com/profile/Quora-Content-Review"
        }
      },
      "url": "https://www.quora.com/How-should-I-start-learning-Python-1"
    }
  ],
  "load_user": null,
  "query": "python",
  "question_limit": 1
}
```

# Features
### Currently implemented
* Search


# Installation
You will need [Python 3](https://www.python.org/download/). [pip](http://pip.readthedocs.org/en/latest/installing.html) is recommended for installing dependencies.
It is recommended that you run in a virtual environment. You can create a virtual environment by running `py -m venv [folder-name]`

- Clone the repo `https://github.com/djunehor/quora-api` and `cd nairaland-api`
- Install requirements `pip install -r requirements.txt`
- If you're on windows, download chrome driver [here](https://chromedriver.chromium.org/) and place in the project directory i.e same place server.py is. For windows, the name should be `chromedriver.exe`
- Rename `.env.example` to `.env` and update with your quora login.
- If you're not on a windows environment, set LINUX=True in the `.env` file
- If on heroku, set config as follows
    - Set environment as Linux => `heroku config: add LINUX=True`
    - Set buildpack 1 => `heroku buildpacks:set https://github.com/heroku/heroku-buildpack-google-chrome`
    - Set buildpack 2 => `heroku buildpacks:set https://github.com/heroku/heroku-buildpack-chromedriver`
    - Set Chrome driver path => `heroku config:set CHROMEDRIVER_PATH=/usr/local/bin/chromedriver`
    - Set Chrome binary path => `heroku config:set GOOGLE_CHROME_BIN=/usr/bin/google-chrome`

To run the API locally:
```bash
$ pip install -r requirements.txt
$ python server.py
```

# Contributing
Feel free to submit a pull request or an issue!  
Nairaland API uses the [quora-api package](https://github.com/djunehor/quora-api).