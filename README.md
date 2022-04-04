# AUTODUB
Setup
Create a new Google Cloud Project.

Enable these Google Cloud APIs:

Speech-to-Text
Text-to-Speech
Translation
From the command line, run:

    gcloud services enable texttospeech.googleapis.com translate.googleapis.com speech.googleapis.com    
Create a new service account with the Translation Admin permission and download it to this directory. Set the environmental variable GOOGLE_APPLICATION_CREDENTIALS to point to your key file:

     export "GOOGLE_APPLICATION_CREDENTIALS" = "./path_to_key.json"
Create a new Google Cloud Storage bucket. We'll need this to store data temporarily while interacting with the Speech API:

 gsutil mkdir MY_BUCKET_NAME
Make a copy of the file .env_template:

 cp .env_template .env
And edit .env, filling in your own values for project id and bucket.

Create a virtualenv:

 python3 -m venv venv
 source ./venv/bin/activate
Install the python dependencies:

 pip install -r requirements.txt
You should be good to go.

 python dubber.py my_movie_file.mp4 "en" outputDirectory --targetLangs '["ja", "es"]'
