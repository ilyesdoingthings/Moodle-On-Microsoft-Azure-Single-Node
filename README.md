# Moodle On Azure Deployment Guide ( Single instance Node ) 
## Microsoft Education for North Africa and Middle East - Tunisia Model


## Introduction 

Moodle is one of the most popular open source learning management platform empowering educators and researchers across the world to disseminate their work efficiently. It is also one of the most matured and robust OSS application which is developed and improvised by the community over the years. We have seen customers deploying Moodle in Azure from small, medium and large enterprises to schools, public sector and government organizations. 
In this blog post, I will be sharing some of the best practices and tips for deploying Moodle on Azure based on our experience working with some of our customers ( tunisia - Minister of Education &  Minister of High Education and Scientific Research ) 

## Create moodle instance on Azure 

the first thing to do is to connect to the Microsoft Azure platform and go to the Marketplace. 
Once logged in, look for the Moodle 4.0 Ready with Ubuntu Server LTS 20.04 module.

![image](https://user-images.githubusercontent.com/26825056/200257894-ea153457-631a-4783-afea-b944cdffe3b1.png)

### PS 

Offered under Microsoft Standard Contract.

This app is only available in Spanish. Moodle is the most widely used learning platform in the world. Start building your online training site in minutes. This image can be deployed on kubernetes, we recommend using Azure Kubernetes Services, although it is compatible with other Kubernetes cloud services. To configure Moodle you will need a Database Server, you can use an Azure Database Server. Easy and intuitive navigation Moodle 4.0 introduces a new design language, visual styling and is responsive and consistent between devices. The new navigation hierarchy is simplified and shows what is contextually relevant. Access to the most commonly used items is delivered through tabbed navigation, which is consistent sitewide. These improvements reduce cognitive load and allow educators and learners to easily find what they want, when they need it. Instructions to start the configuration of the Moodle platform : 1.Got to your browser and type your URL: "http://your-vm-ip/moodle" 2. The image contains the following software: * Moodle 4.0 * PHP 7.4 * Apache 2.4 * Ubuntu Server LTS 20.04 If you have any questions or need more information about the content of this Virtual Machine, please visit our website: http://readymindsitewp.azurewebsites.net/get-started/moodle-ready

## Install the Prerequisites for Moodle 


