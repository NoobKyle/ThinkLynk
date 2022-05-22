---
layout: post
title:  "AWS + Docker"
date:   2020-08-21 05:10:47 +0200
permalink: "/awsdocker"
categories: aws docker
---

![AWS Container Architecture](/ThinkLynk/assets/aws/1.png)

## AWS Elastic Beanstalk

This is a platform within AWS that is used for deploying and scaling web applications. A platform as a service (PaaS) which takes your application code and deploys it while providing the supporting architecture and compute resources required.

### Steps

1. Create Application and give it a name
2. Add Tags to easily identify it
3. Choose the platform (docker in this case)
4. Upload you code

![AWS Container Architecture](/ThinkLynk/assets/aws/2.png)

Now opening the endpoint in a new browser tab will send a get request to the application and revel it with no data (products) in json format

![AWS Container Architecture](/ThinkLynk/assets/aws/3.png)

We will then add data (products) to it by sending post requests using Postman + JSON objects

![AWS Container Architecture](/ThinkLynk/assets/aws/4.png)

Refreshing the browser tab and sending another get request revels the added data (products) for a frontend application to consume.

![AWS Container Architecture](/ThinkLynk/assets/aws/5.png)
