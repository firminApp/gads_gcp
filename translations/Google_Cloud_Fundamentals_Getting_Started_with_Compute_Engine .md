#Google Cloud Fundamentals: Getting Started with Compute Engine

[lab link to qwikslab is here](https://googlepluralsight.qwiklabs.com/focuses/10763035?parent=lti_session)

# Overview
In this lab, you will create virtual machines (VMs) and connect to them. You will also create connections between the instances.
# Objectives
In this lab, you learn how to perform the following tasks:

- Create a Compute Engine virtual machine using the gcloud command-line interface.

- Connect between the two instances.

# steps

### create  virtual machine using command-line interface

- Set default zone
    
        gcloud config set compute/zone us-central1-b
        
- create VM instance

        gcloud compute instances create "my-vm-2" \
        --machine-type "n1-standard-1" \
        --image-project "debian-cloud" \
        --image "debian-9-stretch-v20190213" \
        --subnet "default"
        --tags "http"
        
- create firewall rules:

            gcloud compute firewall-rules create allow-http --action=ALLOW --destination=INGRESS --rules=http:80 --target-tags=http
    