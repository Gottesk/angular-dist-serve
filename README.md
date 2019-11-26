# angular-dist-serve
Nginx configuration for serving Angular build locally under MacOS.
Can be useful for those who need to test ServiceWorker and other PWA features.

## how to use

1. Set up Nginx (if you don't have it)
2. Copy content of nginx.conf into your nginx.conf (I use vscode for this):
```
  sudo code /usr/local/etc/nginx/nginx.conf
```

3. Replace {YOUR_PROJECT_NAME} with your project name, for example project-name
4. Build your application, and then copy dist folder into /var/www/{YOUR_PROJECT_NAME}, can be done vie terminal:
```
  scp -r ~/path-to-your-project/dist/{YOUR_PROJECT_NAME} /var/www/{YOUR_PROJECT_NAME}
```
5. Replace {BACKEND_LOCATION} with your backend api location, for example http://192.168.3.48:7000/
6. Restart nginx via terminal:
```
  sudo nginx -s stop && sudo nginx
```
7. Your dist is available on http://localhost:8080/
8. Profit!

## if you need logs

They are should be there under MacOS:

1. code /usr/local/Cellar/nginx/1.17.3_1/logs/{YOUR_PROJECT_NAME}.access.log
1. code /usr/local/Cellar/nginx/1.17.3_1/logs/{YOUR_PROJECT_NAME}.error.log

if they are not there
```
  sudo mkdir /usr/local/Cellar/nginx/1.17.3_1/logs
  sudo touch /usr/local/Cellar/nginx/1.17.3_1/logs/access.log
  sudo touch /usr/local/Cellar/nginx/1.17.3_1/logs/error.log
  sudo chmod 777 /usr/local/Cellar/nginx/1.17.3_1/logs/*.log
```
