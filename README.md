# Overview
Building a CI/CD pipeline with GitHub Actions and Azure Pipelines.

## Project Plan
Project plan is distributed among different stages and timeline. Please refer to Excel sheet.
https://researchtriangleinstitute-my.sharepoint.com/:x:/g/personal/kpatel_rti_org/EQrAeu2-kLtKnvCk-dxWIRQBjNheZCtcbY3bpU_I1NxhGg?e=uDF7t0

We will be tracking the progress of project via Trello board.
https://trello.com/b/bHPOgaQs

## Instructions
Architectural Diagram for Agile project management can be found at below link.
https://video.udacity-data.com/topher/2020/July/5f21ce4e_building-a-ci-cd-pipeline/building-a-ci-cd-pipeline.png

<TODO:  Instructions for running the Python project.  How could a user with no context run this project without asking you for any help.  Include screenshots with explicit steps to create that work. Be sure to at least include the following screenshots:
Familiarity with Azure portal, Azure cloud shell and GitHub is required.

Step 1 - Build a Github repository.
Step 2 - Launch Azure Cloud Shell environment and clone the repository from Github.
Step 3 - Create the Makefile, used to create shortcuts to build, test and deploy a project.
Step 4 - Create Requirements text file, it is a convenient way to list what packages a project needs.
Step 5 - Create a Python virtual environment. Commands shown below.
         python3 -m venv ~/.myrepo
         source ~/.myrepo/bin/activate
Step 6 - Create Script and test files and add to Git repo.
Step 7 - Run command "make all" to test the functioning of "makefile".
Step 8 - Enable Github Actions from your Github account under your repository.
Step 9 - Update the yml code for the Github Action workflow.
Step 10 - Verify the workflow runs and completes successfully via Github UI.
Step 11 - Create a WebApp (in this case it will be a Linux OS with Python installation).
Step 12 - Integrate WebApp with Github repository as the source of deployment.
Step 13 - Making Prediction .....
         To make a prediction, you have to open a separate tab or terminal window. In this new window, navigate to the main project directory
         (some computers will do this automatically) and call ./make_prediction.sh if testing locally, or modify make_predict_azure_app.sh.
Step 14 - Inspect logs of running application - https://<app-name>.scm.azurewebsites.net/api/logs/docker replace "app-name" with your web app name.
          or can stream them - az webapp log tail.
Step 15 - Enable continuous deployment with Azure Pipelines.





  


* Project running on Azure App Service

* Project cloned into Azure Cloud Shell

* Passing tests that are displayed after running the `make all` command from the `Makefile`

* Output of a test run

* Successful deploy of the project in Azure Pipelines.  [Note the official documentation should be referred to and double checked as you setup CI/CD](https://docs.microsoft.com/en-us/azure/devops/pipelines/ecosystems/python-webapp?view=azure-devops).

* Running Azure App Service from Azure Pipelines automatic deployment

* Successful prediction from deployed flask app in Azure Cloud Shell.  [Use this file as a template for the deployed prediction](https://github.com/udacity/nd082-Azure-Cloud-DevOps-Starter-Code/blob/master/C2-AgileDevelopmentwithAzure/project/starter_files/flask-sklearn/make_predict_azure_app.sh).
The output should look similar to this:

```bash
udacity@Azure:~$ ./make_predict_azure_app.sh
Port: 443
{"prediction":[20.35373177134412]}
```

* Output of streamed log files from deployed application

kalpesh@Azure:~/udacity-proj02$ az webapp log tail
2020-12-04T08:47:19  Welcome, you are now connected to log-streaming service.
Starting Log Tail -n 10 of existing logs ----
2020-12-04T07:39:30.430077494Z 172.16.2.1 - - [04/Dec/2020:07:39:30 +0000] "GET / HTTP/1.1" 200 32 "https://portal.azure.com/" "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/86.0.4240.198 Safari/537.36"
2020-12-04T07:39:51.057603555Z
2020-12-04T07:39:51.057643155Z   _____
2020-12-04T07:39:51.057673955Z   /  _  \ __________ _________   ____
2020-12-04T07:39:51.057678455Z  /  /_\  \___   /  |  \_  __ \_/ __ \
2020-12-04T07:39:51.057682455Z /    |    \/    /|  |  /|  | \/\  ___/
2020-12-04T07:39:51.057686355Z \____|__  /_____ \____/ |__|    \___  >
2020-12-04T07:39:51.057690355Z         \/      \/                  \/
2020-12-04T07:39:51.057694155Z
2020-12-04T07:39:51.057697655Z A P P   S E R V I C E   O N   L I N U X
2020-12-04T07:39:51.057701255Z
2020-12-04T07:39:51.057704555Z Documentation: http://aka.ms/webapp-linux
2020-12-04T07:39:51.057708055Z Python 3.7.9
2020-12-04T07:39:51.057711555Z Note: Any data outside '/home' is not persisted
2020-12-04T07:39:51.177504951Z Starting OpenBSD Secure Shell server: sshd.
2020-12-04T07:39:51.200239508Z App Command Line not configured, will attempt auto-detect
2020-12-04T07:39:51.201147610Z Launching oryx with: create-script -appPath /home/site/wwwroot -output /opt/startup/startup.sh -virtualEnvName antenv -defaultApp /opt/defaultsite -bindPort 8000
2020-12-04T07:39:51.221026459Z Found build manifest file at '/home/site/wwwroot/oryx-manifest.toml'. Deserializing it...
2020-12-04T07:39:51.224828868Z Build Operation ID: |ysozZBF4Lsc=.2d5bbd63_
2020-12-04T07:39:51.226205272Z Oryx Version: 0.2.20200917.1, Commit: 59deb778658a124cb74ea8e2c8f39fa87abcc9d9, ReleaseTagName: 20200917.1
2020-12-04T07:39:51.914589873Z Detected an app based on Flask
2020-12-04T07:39:51.921278189Z Generating `gunicorn` command for 'app:app'
2020-12-04T07:39:52.529691193Z Writing output script to '/opt/startup/startup.sh'
2020-12-04T07:39:52.756773754Z Found virtual environment .tar.gz archive.
2020-12-04T07:39:52.757326856Z Removing existing virtual environment directory /antenv...
2020-12-04T07:39:52.764786374Z Extracting to directory /antenv...
2020-12-04T07:39:58.106567563Z Using packages from virtual environment antenv located at /antenv.
2020-12-04T07:39:58.109099669Z Updated PYTHONPATH to ':/antenv/lib/python3.7/site-packages'
2020-12-04T07:39:59.844948574Z [2020-12-04 07:39:59 +0000] [40] [INFO] Starting gunicorn 20.0.4
2020-12-04T07:39:59.845743576Z [2020-12-04 07:39:59 +0000] [40] [INFO] Listening at: http://0.0.0.0:8000 (40)
2020-12-04T07:39:59.846081576Z [2020-12-04 07:39:59 +0000] [40] [INFO] Using worker: sync
2020-12-04T07:39:59.854156696Z [2020-12-04 07:39:59 +0000] [43] [INFO] Booting worker with pid: 43
2020-12-04T07:40:07.939471282Z 172.16.2.1 - - [04/Dec/2020:07:40:07 +0000] "GET /robots933456.txt HTTP/1.1" 404 232 "-" "-"
2020-12-04T07:40:34.613966513Z 172.16.2.1 - - [04/Dec/2020:07:40:34 +0000] "GET / HTTP/1.1" 200 32 "-" "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/86.0.4240.198 Safari/537.36"
2020-12-04T07:42:45.638799854Z 172.16.2.1 - - [04/Dec/2020:07:42:45 +0000] "GET / HTTP/1.1" 200 32 "-" "AlwaysOn"
2020-12-04T07:47:45.789853036Z 172.16.2.1 - - [04/Dec/2020:07:47:45 +0000] "GET / HTTP/1.1" 200 32 "-" "AlwaysOn"
2020-12-04T07:52:45.968974489Z 172.16.2.1 - - [04/Dec/2020:07:52:45 +0000] "GET / HTTP/1.1" 200 32 "-" "AlwaysOn"
2020-12-04T07:57:46.148634646Z 172.16.2.1 - - [04/Dec/2020:07:57:46 +0000] "GET / HTTP/1.1" 200 32 "-" "AlwaysOn"
2020-12-04T08:02:46.366706456Z 172.16.2.1 - - [04/Dec/2020:08:02:46 +0000] "GET / HTTP/1.1" 200 32 "-" "AlwaysOn"
2020-12-04T08:07:46.515000682Z 172.16.2.1 - - [04/Dec/2020:08:07:46 +0000] "GET / HTTP/1.1" 200 32 "-" "AlwaysOn"
2020-12-04T08:12:46.724282922Z 172.16.2.1 - - [04/Dec/2020:08:12:46 +0000] "GET / HTTP/1.1" 200 32 "-" "AlwaysOn"
2020-12-04T08:17:46.916514874Z 172.16.2.1 - - [04/Dec/2020:08:17:46 +0000] "GET / HTTP/1.1" 200 32 "-" "AlwaysOn"
2020-12-04T08:22:47.180689171Z 172.16.2.1 - - [04/Dec/2020:08:22:47 +0000] "GET / HTTP/1.1" 200 32 "-" "AlwaysOn"
2020-12-04T08:27:47.286129309Z 172.16.2.1 - - [04/Dec/2020:08:27:47 +0000] "GET / HTTP/1.1" 200 32 "-" "AlwaysOn"
2020-12-04T08:28:32.201301630Z [2020-12-04 08:28:32,201] INFO in app: JSON payload: %s json_payload
2020-12-04T08:28:32.203774336Z [2020-12-04 08:28:32,203] INFO in app: inference payload DataFrame: %s inference_payload
2020-12-04T08:28:32.204389338Z [2020-12-04 08:28:32,203] INFO in app: Scaling Payload: %s payload
2020-12-04T08:28:32.226534092Z 172.16.2.1 - - [04/Dec/2020:08:28:32 +0000] "POST /predict HTTP/1.1" 200 35 "-" "curl/7.47.0"
2020-12-04T08:32:00.480954258Z 172.16.2.1 - - [04/Dec/2020:08:32:00 +0000] "GET / HTTP/1.1" 200 32 "https://portal.azure.com/" "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/86.0.4240.198 Safari/537.36"
2020-12-04T08:32:47.531150381Z 172.16.2.1 - - [04/Dec/2020:08:32:47 +0000] "GET / HTTP/1.1" 200 32 "-" "AlwaysOn"
2020-12-04T08:37:47.650234113Z 172.16.2.1 - - [04/Dec/2020:08:37:47 +0000] "GET / HTTP/1.1" 200 32 "-" "AlwaysOn"
2020-12-04T08:40:51.684321768Z 172.16.2.1 - - [04/Dec/2020:08:40:51 +0000] "GET / HTTP/1.1" 200 32 "https://portal.azure.com/" "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/86.0.4240.198 Safari/537.36"
2020-12-04T08:42:47.862257704Z 172.16.2.1 - - [04/Dec/2020:08:42:47 +0000] "GET / HTTP/1.1" 200 32 "-" "AlwaysOn"
/home/LogFiles/__lastCheckTime.txt  (https://flaskhellokay.scm.azurewebsites.net/api/vfs/LogFiles/__lastCheckTime.txt)
12/4/20 7:36:25 AM
2020-12-04T07:39:49.760Z INFO  - Starting container for site
2020-12-04T07:39:49.761Z INFO  - docker run -d -p 3260:8000 --name flaskhellokay_1_4d978642 -e WEBSITE_SITE_NAME=flaskhellokay -e WEBSITE_AUTH_ENABLED=False -e WEBSITE_ROLE_INSTANCE_ID=0 -e WEBSITE_HOSTNAME=flaskhellokay.azurewebsites.net -e WEBSITE_INSTANCE_ID=7254a188ab4586854ad76076414307db730ca9c4cf4a65f1d2870b4c9a2ed8a8 -e HTTP_LOGGING_ENABLED=1 appsvc/python:3.7_20200918.1
2020-12-04T07:39:50.976Z INFO  - Initiating warmup request to container flaskhellokay_1_4d978642 for site flaskhellokay
2020-12-04T07:40:07.936Z INFO  - Container flaskhellokay_1_4d978642 for site flaskhellokay initialized successfully and is ready to serve requests.
Ending Log Tail of existing logs ---

Starting Live Log Stream ---

2020-12-04T08:47:48.039431220Z 172.16.2.1 - - [04/Dec/2020:08:47:48 +0000] "GET / HTTP/1.1" 200 32 "-" "AlwaysOn"
> 

## Enhancements

<TODO: A short description of how to improve the project in the future>

## Demo 

<TODO: Add link Screencast on YouTube>


