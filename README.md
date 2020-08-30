# MoM.ai
AI enabled webapp for Speaker Diarization, Audio trascrption with time stamps and palceholder for every speakers' name and MoM summary.

## System Requirements

Ubuntu

Python 3

At least 8GB of RAM 

At least 2GB of free disk space

## Installation

Clone the git repo and navigate to the project root

Setup a virtual python environment if required

Install redis server if don't already have it. The server should run on localhost:6379
```
sudo apt-get update
sudo apt-get install redis-server
```

Use the python package manager pip to install MOM.ai python requirements.
```
pip install -r requirements.txt
```

Run django migrations to update the database
```
python manage.py makemigrations
python manage.py migrate
```

Start the celery workers as background tasks by running the command:
```
nohup celery -A prototype worker -l info &
```

Finally run the django development server
```
python manage.py runserver
```

## Usage
By default the development server runs on 127.0.0.1:8000

In a browser navigate to http://127.0.0.1:8000/home to begin using the app

You may only upload .wav file for processing

The web app will take some time to load when running for the first time as it has to download an AI model of 1.2GB size.




