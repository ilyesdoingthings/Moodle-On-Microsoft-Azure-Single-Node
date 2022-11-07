# Moodle on Azure Deployment Guide ( Single instance Node ) 🥇
## Microsoft Education for North Africa and Middle East - Tunisian Model 🚩

![image](https://user-images.githubusercontent.com/26825056/200283591-423619fe-2d49-42a1-b25e-b7a9429e4cde.png)

## Introduction 👇

Moodle is one of the most popular open source learning management platform empowering educators and researchers across the world to disseminate their work efficiently. It is also one of the most matured and robust OSS application which is developed and improvised by the community over the years. We have seen customers deploying Moodle in Azure from small, medium and large enterprises to schools, public sector and government organizations. 
In this blog post, I will be sharing some of the best practices and tips for deploying Moodle on Azure based on our experience working with some of our customers ( tunisia - Minister of Education &  Minister of High Education and Scientific Research ) 

## Create moodle instance on Azure ☁️

the first thing to do is to connect to the Microsoft Azure platform and go to the Marketplace. 
Once logged in, look for the Moodle 4.0 Ready with Ubuntu Server LTS 20.04 module.

![image](https://user-images.githubusercontent.com/26825056/200257894-ea153457-631a-4783-afea-b944cdffe3b1.png)

### PS - Offered under Microsoft Standard Contract.

Instructions to start the configuration of the Moodle platform : 
1.Got to your browser and type your URL: "http://your-vm-ip/moodle" 
2. The image contains the following software: * Moodle 4.0 * PHP 7.4 * Apache 2.4 * Ubuntu Server LTS 20.04 .
3. If you have any questions or need more information about the content of this Virtual Machine, please visit our website: http://readymindsitewp.azurewebsites.net/get-started/moodle-ready

![image](https://user-images.githubusercontent.com/26825056/200260974-f80e33f0-8e1b-4c00-ba43-cbb518ea863d.png)
![image](https://user-images.githubusercontent.com/26825056/200261796-70373319-370b-40eb-b31e-a48e993e4de3.png)

## Install the Prerequisites for Moodle 

Install the prerequisites for Moodle. This includes software and PHP modules that support Moodle’s features and Git for installing Moodle and keeping it up to date.

```
sudo apt install graphviz aspell ghostscript clamav php7.4-pspell php7.4-curl php7.4-gd php7.4-intl php7.4-mysql php7.4-xml php7.4-xmlrpc php7.4-ldap php7.4-zip php7.4-soap php7.4-mbstring git
```

