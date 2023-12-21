# CuacaTani-CC
Bangkit 2023 Product-based Capstone Project - CuacaTani - CC

This is Cloud Computing repository for CuacaTani application.

# Deployment
* **Google Cloud Platform (GCP)**
  * **Prerequisites** 
    <br>
    Here are several points to consider before proceeding:
    * Install or update to the latest version of the **Google Cloud CLI**
    * Set a default region and zone `asia-southeast2-a`
    * Enable **Compute Engine** and **App Engine** APIs 
      <br><br>
* **Google App Engine (GAE)**
    <br>
    Google App Engine (GAE) is a platform as a service (PaaS) provided by the Google Cloud Platform (GCP). GAE enables developers to build and deploy web applications without the need to manage infrastructure or servers directly.
    <br><br>
    To deploy an application through GAE,
    * On GCP console, go to **Navigation Menu -> App Engine**
    * Click **Create Application**
    * Activate **Cloud Shell**
    * Go to the CuacaTani folder
      ````
      cd CuacaTani
      ````
    * Make sure that you have a `app.yaml` file using the `ls` command on **Cloud Shell**
    * Example app.yaml file
      ````
      runtime: python
      env: flex
      entrypoint: gunicorn -b :$PORT main:app

      env_variables:
       SECRET_KEY: 'cuacatani'

      runtime_config:
       python_version: '3.7'

      automatic_scaling:
       target_concurrent_requests: 10

      ````
     * Deploy app to App Engine
       ```
       gcloud app deploy
       ```
     * If any prompt shown press `Y` and click enter
     * View Deployed App after successfully deployed
       ```
       gcloud app browse
       ```
