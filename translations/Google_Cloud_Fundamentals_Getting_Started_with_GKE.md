#Google Cloud Fundamentals: Getting Started with GKE

## Overview
In this lab, you create a Google Kubernetes Engine cluster containing several containers, each containing a web server. You place a load balancer in front of the cluster and view its contents.

## Objectives
In this lab, you learn how to perform the following tasks:

- Provision a Kubernetes cluster using Kubernetes Engine.

- Deploy and manage Docker containers using kubectl.

[ lab Link to qwikslab is here](https://googlepluralsight.qwiklabs.com/focuses/10750085?parent=lti_session)

## Start a Kubernetes Engine cluster

 this command will set default zone in envaroment variable MY_ZONE, create a container cluster names webfrontend with two nodes
        
        export MY_ZONE=us-central1-a
        gcloud container clusters create webfrontend --zone $MY_ZONE --num-nodes 2
 
 ##  Run and deploy a container
       
        kubectl create deploy nginx --image=nginx:1.17.10   
        kubectl expose deployment nginx --port 80 --type LoadBalancer
        kubectl scale deployment nginx --replicas 3    