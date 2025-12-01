---
layout: page
show_meta: false
title: "Application Server Installation"
subheadline: ""
header:
  image_fullwidth: architecture/architecture.jpg
permalink: "/appServerInstall/"
---

<div align="center">
    <a href="#" data-reveal-id="videoModal5" onclick="toppy(5)" >
        <img src="/images/installThumb2.png" width="450" height="253" alt="" style="border: 5px solid #89bee6;"/>
    </a>
</div>
<br>

This tutorial will show you how to install Blinky-Lite on a [Ubuntu Server](https://ubuntu.com/download/server) that is installed on amd64 or x86_64. The server should have at least 2048MB of memory and 20GB of disk space.

## Installing Portainer
Blinky-Lite is composed of a number of Docker containers. We use a web based tool called [Portainer](https://www.portainer.io/) to install and orchestrate the containers. From a terminal on your application server, retrieve the Blinky-Lite Portainer installation script

<code>wget https://raw.githubusercontent.com/Blinky-Lite/blinky-compose/main/scripts/installDockerPortainer.sh</code>

Give the script execution privileges

<code>chmod +x installDockerPortainer.sh</code>

Run the script and supply a password for administering the Portainer web app. The password must be at least 12 characters long. 

<code>./installDockerPortainer.sh <i>doNotUseThisPassword</i></code>

The script will take a while to execute and give a message

<i>...Finished installing docker..serving Portainer on port 9000</i>

when complete.

## Configure the blinky-Lite stack
Open your web browser and in the address bar enter the IP address of your Ubuntu server followed by a :9000 to navigate to the Portainer web app.
- The username for Portainer is admin and the password is what you entered during the installation script. 
- Click on the "Get Started" button and then click on the Docker icon to reach the Docker dashboard. 
- From the Docker dashboard click on the "stacks" button. 
- Press the blue "Add Stack" button and enter the name for your Blinky-Lite stack. 
- It is recommended to use blinky-lite as the stack name. 
- Click on the Web Editor option and then and then copy this [template stack file](https://raw.githubusercontent.com/Blinky-Lite/blinky-compose/refs/heads/main/blinky-lite.yaml) into the web editor. 


### Configure the Blinky-Lite env variables
- Underneath the Web Editor in the Environment variables section, click on the *Advanced mode* link.
- Open this [template env file](https://raw.githubusercontent.com/Blinky-Lite/blinky-compose/refs/heads/main/env/blinky-lite.env) and copy it into the env window in Portainer
- In the Portainer window, view the env variables in *Simple mode* by clicking on the Simple mode link, 

Fill in the environment variables into the table as shown. 

* `DOCKER_TAG` - Enter *amd64*  or *arm64v8* depending on your computer architecture.
* `BLINKYLITE_PASSWORD` - this password will be used for the database and mqtt broker. For simplicity, you can use the sme password as used for the Portainer container.
* `BOX` - name of your blinky-lite box eg. my-blinky-box-01
* `REMOTE_MQTTSERVER` - Enter *NONE*. Since this is an introductory tutorial we will not use an external MQTT broker as a bridge
* `REMOTE_MQTTUSER` - Enter *NONE*
* `REMOTE_MQTTPASSWORD` - Enter *NONE*
* `HUB` - Enter `blinky-hub`
* `EXTRA_HUB_TOPIC1` - Enter *NONE*
* `JWTKEYSECRET` - Used to encrypt communications between the client web apps and the server. 
  - You can use [online tools](https://jwtsecrets.com/) to generate a secret.
  - 64 bits or 16 characters should be sufficient.
* `MAXDBSIZE` - The maximum size of the database in bytes. *4500000000* is a good size to start.
* `TWOFA` - The two factor authentication flag. For simplicity, set to *0* for password authentication.
* `CUSTOM_LAUNCH` - For simplicity, we will use the default landing page so set this to *0*.
* `GIT_REPO_URL` - Only needed for a custom launch so set to *NONE*
* `GIT_BRANCH`- Only needed for a custom launch so set to *NONE* 
* `GIT_STATIC_CONTENT`- Only needed for a custom launch so set to *NONE* 
* `ENABLE_NODERED_EDITOR` - For advanced use only so set this to *0* 


## Starting the blinky-lite stack
At the bottom of the stack configuration web page, press the blue deploy the stack button. It will take some time to deploy the stack because all the necessary docker containers need to be imported.  Once the stack has been deployed, you will see blinky-lite show up on the stacks list.  

Blinky-Lite will be served on port 80 of the Ubuntu server. Because blinky-lite implements an nginx reverse proxy server, you can also reach the Portainer web application by entering portainer after the server ip address. 

## Viewing the Blinky-Lite database
You can also edit the blinky-lite database by entering mongo-express after the server ip address. The user name for mongo-express is admin and the password is the same as the blinky-lite password you set when configuring the stack. You should only touch the blinky-lite database. 

The blinky-lite database contains a number of mongo-db collections. For example, you can change user credentials and permissions in users collections.  You can set the color scheme of all the applications by adjusting the general app document. You can also adjust the look of the initial landing page. 




<div id="videoModal5" class="reveal-modal large" data-reveal="">
  <div class="flex-video widescreen vimeo" style="display: block;">
    <iframe width="1280" height="720" src="https://player.vimeo.com/video/906812514?dnt=1" frameborder="0" allowfullscreen></iframe>
  </div>
  <a class="close-reveal-modal">&#215;</a>
</div>
