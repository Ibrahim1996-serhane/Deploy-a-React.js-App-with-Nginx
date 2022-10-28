# Deploy-a-React.js-App-with-Nginx
----------------------------------

## Step 1 — start  a React Project
### npm start
### npm run build

## Step 2 — Configure Nginx to Deploy React App
### apt-get install nginx python3-certbot-nginx -y
### mkdir /var/www/html/react
### apt-get install nginx python3-certbot-nginx -y
### mkdir /var/www/html/react
### {Directory:/App/frontend/}
### cp -r build/* /var/www/html/react/
### nano /etc/nginx/conf.d/react.conf
### <br/> 
    server   
    {
        listen 80;
        listen [::]:80;
        root /var/www/html/react/;
        index index.html index.htm;
        # MODIFY SERVER_NAME EXAMPLE
        proxy_cache_bypass $http_upgrade;
        server_name react.ejemplo.com;
        location / {
        try_files $uri $uri/ =404;
        }  
    }
  



