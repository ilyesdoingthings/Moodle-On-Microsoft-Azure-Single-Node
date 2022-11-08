# Moodle on Azure Deployment Guide ( Single instance Node ) 
## Microsoft Education for North Africa and Middle East - Microsoft Azure Technical Tunisian Model for MoE and MoHE

![image](https://user-images.githubusercontent.com/26825056/200283591-423619fe-2d49-42a1-b25e-b7a9429e4cde.png)

## Prerequisites

In order to deploy, customize and consume this solution, it is important you have good understanding of Azure Resource Manager (ARM) templates.
you can visit this URL to read about https://learn.microsoft.com/en-us/azure/azure-resource-manager/templates/overview

## Provisioning a Scalable Moodle Cluster on Azure 

If you have Azure account, you can deploy Moodle via the Azure portal, or you can deploy Moodle via the CLI. 
Please note that while you can use an Azure free account to get started depending on which template configuration you choose you will likely be required to upgrade to a paid account.

Below is a list of pre-defined deployment options based on typical deployment scenarios (i.e. dev/test, production etc.). All configurations are fixed, and you just need to pass your ssh public key to the template for logging in to the deployed VMs. For production deployments, large size or Maximum template below is highly recommended which provisions high performance SKUs and configures the environment for high availability.

to read more, you can visit 👇
https://techcommunity.microsoft.com/t5/azure-database-for-mysql-blog/deploying-moodle-on-azure-things-you-should-know/ba-p/814054

## Introduction 

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

1. Install the prerequisites for Moodle. This includes software and PHP modules that support Moodle’s features and Git for installing Moodle and keeping it up to date.

```
sudo apt install graphviz aspell ghostscript clamav php7.4-pspell php7.4-curl php7.4-gd php7.4-intl php7.4-mysql php7.4-xml php7.4-xmlrpc php7.4-ldap php7.4-zip php7.4-soap php7.4-mbstring git
```

2. Restart Apache to load the modules.

```
sudo systemctl restart apache2
```

## Download Moodle Package 

1. Change into the /opt directory, clone the Moodle Git repository and change into the resulting moodle subdirectory.

```
cd /opt
sudo git clone git://git.moodle.org/moodle.git
cd moodle
```

2. Determine the latest stable Moodle release from Moodle’s official list of releases. At the time of writing, the latest stable release is 4.0.

3. The following command lists the branches in the Git repository. From that list, identify the branch associated with the latest stable release. For release 4.0, this is MOODLE_400_STABLE.

```
sudo git branch -a
```

![image](https://user-images.githubusercontent.com/26825056/200318904-fed98e99-3835-42ab-b92f-16230e928046.png)


4. Track and then check out the branch you identified.

```
sudo git branch --track MOODLE_400_STABLE origin/MOODLE_400_STABLE
sudo git checkout MOODLE_400_STABLE
```

![image](https://user-images.githubusercontent.com/26825056/200319648-fb7f00c9-7a29-4635-bf13-7ac1d5eb4db9.png)

5. Copy the directory with the Moodle repository into the /var/www/html directory. Then, modify the new Moodle directory’s permissions to grant read, execute, and write access to any user.

```
sudo cp -R /opt/moodle /var/www/html/
 sudo chmod -R 0777 /var/www/html/moodle
```

6. Create a /var/moodledata directory, make www-data its owner, and modify its permissions to grant all users read, execute, and write access.

```
sudo mkdir /var/moodledata
sudo chown -R www-data /var/moodledata
sudo chmod -R 0777 /var/moodledata
 ```
 
 ## Set Up the MySQL Server for Moodle Instance 
 
 1. Open the MySQL interface as the root user.
 
 ```
 sudo mysql -u root
 ```
2. Use the following MySQL command to create a database for Moodle.

```
CREATE DATABASE moodle DEFAULT CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
```

3. Create a Moodle MySQL user, and give it the required permissions on the Moodle database. In the following example, replace moodle-user and password with the username and password, respectively, you would like to use for the Moodle MySQL user.

```
CREATE USER 'moodle-user'@'localhost' IDENTIFIED BY 'password';
GRANT SELECT,INSERT,UPDATE,DELETE,CREATE,CREATE TEMPORARY TABLES,DROP,INDEX,ALTER ON moodle.* TO 'moodle-user'@'localhost';
```

4. Exit the MySQL interface using the quit command.

![dzzdzdzdzdzdzdz](https://user-images.githubusercontent.com/26825056/200581760-c0350929-14c7-4e3b-aa56-c404763c44b9.png)

## Complete the Moodle Installation 

1. In a web browser, navigate to the Moodle URL, which is your server’s domain name followed by /moodle. So, if your server’s domain name is example.com, then the Moodle URL would be example.com/moodle.

![image](https://user-images.githubusercontent.com/26825056/200580493-21554fbf-1bcb-438e-856e-95d9e59073c2.png)

2. Follow the prompts to complete the Moodle setup.
