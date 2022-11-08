# Set Up an SSL Certificate

![image](https://user-images.githubusercontent.com/26825056/200593974-b145f98c-88a9-417d-9f44-0047a9feb859.png)

Although not required, it is recommended that you secure your Moodle site using an SSL certificate. 

This guide uses Certbot to create a free certificate from Let’s Encrypt.

for more information about Certbot, visit https://certbot.eff.org 
for more information about let(s Encrypt, visit https://letsencrypt.org

1. Update the Snap app store. Snap provides application bundles that work across major Linux distributions and is installed by default with all Ubuntu releases since 16.04.

```
sudo snap install core && sudo snap refresh core
```

![image](https://user-images.githubusercontent.com/26825056/200593718-66c262d6-3660-4dc8-9e6b-4903ef920e62.png)

2. Remove any existing Certbot installation.

```
sudo apt remove certbot
```

3. Install Certbot.

```
sudo snap install --classic certbot
```

![image](https://user-images.githubusercontent.com/26825056/200594572-dcdfeb85-4b85-461f-a3f1-98224c1f1780.png)

4. Download a certificate for your site.

```
sudo certbot --apache
```
--> Certbot prompts you to enter your site’s domain name. Do so to complete the installation of the SSL certificate.

![image](https://user-images.githubusercontent.com/26825056/200595624-8e29f722-6d7a-46e6-ab1f-3ebe9ec0a81d.png)

5. Using your preferred text editor, open the Moodle configuration file, /var/www/html/moodle/config.php. Change the $CFG->wwwroot value to use https instead of http. Replace example.com in the following example with your site’s domain name.

![image](https://user-images.githubusercontent.com/26825056/200600010-4ddadff8-4f4b-410e-8d8c-9eb4c9d9eb25.png)

6. Restart the Apache server.

```
 sudo systemctl restart apache2
```
