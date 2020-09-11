#Google Cloud Fundamentals: Getting Started with App Engine

[lab link  to qwikslab is here](https://googlepluralsight.qwiklabs.com/focuses/10763035?parent=lti_session)

# Overview
In this lab, you create and deploy a simple App Engine application using a virtual environment in the Google Cloud Shell.

# Objectives
In this lab, you learn how to perform the following tasks:

- Initialize App Engine.

- Preview an App Engine application running locally in Cloud Shell.

- Deploy an App Engine application, so that others can reach it.

- Disable an App Engine application, when you no longer want it to be visible.

## Initialize App Engine

         export PROJECT_ID= my_projetc_id
         gcloud app create --project=$PROJECT_ID --region=us-central1
         git clone https://github.com/GoogleCloudPlatform/python-docs-samples
         cd python-docs-samples/appengine/standard_python3/hello_world
         
##Run Hello World application locally

          sudo apt-get update
          sudo apt-get install virtualenv
          virtualenv -p python3 venv
          source venv/bin/activate
          pip install  -r requirements.txt
          python main.py
          
## Deploy and run Hello World on App Engine

            cd ~/python-docs-samples/appengine/standard_python3/hello_world
            gcloud app deploy