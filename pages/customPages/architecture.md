---
layout: page
show_meta: false
title: "Architecture"
subheadline: ""
header:
  image_fullwidth: architecture/architecture.jpg
permalink: "/architecture/"
---

<div align="center">
    <a href="#" data-reveal-id="videoModal4" onclick="toppy(4)" >
        <img src="/images/archThumb2.png" width="450" height="253" alt="" style="border: 5px solid #89bee6;"/>
    </a>
</div>
<br>
From isolated container networks, to publish-subscribed device communication, to role-based authentication via jason web tokens, to virtual private network communication through a reverse proxy server, Blinky-Lite provides an organised, layered approach to remote access security.

![](/images/architecture/architecture.png)  
<span style="color:#ff6100">Blinky-Lite Architecture</span>

## Containers

The Blinky-Lite architecture is based on Linux containers. A Linux container is a set of one or more processes that are isolated from the rest of the system. All the files necessary to run them are provided from a distinct image, meaning Linux containers are portable and consistent. Because of their popularity and ease of use, Linux containers make Blinky-Lite very extendable. Containers are also an important part of IT security. For example, all the Linux containers in Blinky-Lite communicate on an isolated container network. 

Blinky-Lite Linux containers are managed by Portainer which itself is a linux container with an easy-to-use web interface. The core containers of Blinky-Lite are the application server, the database for storing data and application configuration, and the notification server for alarm handling.

![](/images/architecture/portainer.png)  
<span style="color:#fdc100">Portainer container in Blinky-Lite</span>

## Communication Protocol

To communicate with internal devices, Blinky-Lite uses an MQTT container. MQTT is a  publish-subscribe communication protocol developed by IBM for the monitoring of  oil pipelines running through the desert, but is now a very popular IoT communication protocol. A key security feature of MQTT is that every device initiates authentication to the communication broker, and the publish-subscribe topics for each device are linked to a unique device authentication. This is much different than most other control system protocols in which communication to the device is initiated externally, which can compromise security. Also, In traditional systems, devices can be overwhelmed by too many requests for data. However, MQTT provides inherent data pooling. That is, devices only publish data when they are ready, regardless of how many requests from users.

![](/images/architecture/architecture.jpg)  
<span style="color:#fdc100">Blinky-Lite MQTT Communications</span>

## Security

### Role Based Access

With Blinky-Lite, the user can only interact with the control system through applications served from the application server. The user accesses the web applications through a reverse proxy server that is configured to permit only appropriate routing requests from the user.

Next in the line of defence is role-based authentication.  In the Blinky-Lite database, roles or permissions are assigned for each user.  These roles limit which applications a user can use, what the user can do in each application, such as read or write, and what data types and data the user can interact with.

![](/images/architecture/userRoles.png)  
<span style="color:#fdc100">Role based access database</span>

When a user logs into the control system with two factor authentication, their credentials are matched against those stored in the user database. The user’s roles that are defined in the user database are encrypted  in a Jason web token. This token is then sent back to the user and is stored  as an encrypted cookie in her browser. Each time the user interacts with the application server, she presents the encrypted token, and the server decides whether the request can be granted, based on the user’s allowed roles.

![](/images/architecture/authFlow.png)  
<span style="color:#fdc100">User authentication flow.</span>

### One way reverse proxy
At this point, Blinky-Lite is perfectly suited for operations inside an internet firewall. However, a remote access control platform is not of much use if it  cannot be securely accessed from outside the user’s facility. For secure remote access, Blinky lite provides a tunnel container that sends traffic through the firewall,  using a virtual private network. Now, Blinky-Lite goes one step further by routing the VPN to an outbound-only, reverse proxy server, located in the cloud, such as Cloudflare zero trust. This reverse proxy server permits only allowed routes to the application server,  and provides the first line of defence against the wild-world of the internet, such as denial-of-service attacks.

### External MQTT Brokers
Because Blinky-Lite uses MQTT as its device communication protocol, Blinky-Lite can be easily extended to a multi-node distributed control platform, by bridging multiple Blinky-Lite systems to an external MQTT broker. By configuring the topics on the external broker, it is possible to share  only a certain subset of devices between Blinky-Lite systems. This configuration provides an excellent balance between data sharing and compartmentalising. Note, again, that connections to the external broker are initiated from the internal brokers, providing a secure connection.

<div id="videoModal4" class="reveal-modal large" data-reveal="">
  <div class="flex-video widescreen vimeo" style="display: block;">
    <iframe width="1280" height="720" src="https://player.vimeo.com/video/913220335?dnt=1" frameborder="0" allowfullscreen></iframe>
  </div>
  <a class="close-reveal-modal">&#215;</a>
</div>
