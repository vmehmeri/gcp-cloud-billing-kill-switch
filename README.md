# gcp-cloud-billing-kill-switch
A Cloud Function that can triggered by a Cloud Billing budget alert to automatically disable Cloud Billing in a project.

> [!WARNING]
> Disabling billing accounts on a project will shut down all existing resources and it's unlikely you will be able to recover them. Proceed with caution. 

## Pre-requisites
You should have an existing GCP project and billing account configured. You need to have the right IAM permissions to grant the Cloud Run Function's service account the role of Billing Administrator on the Billing Account (typically, either the **Owner** or **Security Admin** IAM roles).

## Instructions
- Step 1: Create the function with the code in this repository (note: Choose the `require authentication` option when deploying the function)
- Step 2: Configure a Cloud Pub/Sub topic and push subscription. The push subscription should be configured with the function's URL as the endpoint and a service account with Cloud Run Invoker permission. 
- Step 3: Create budget and alerts. Configure alerts to publish a message to the Pub/Sub topic previously created. 

You can see a full walkthrough in this Youtube video:

TBD
