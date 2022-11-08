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

