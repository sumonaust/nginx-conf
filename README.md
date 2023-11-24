events {
#empty
}

http {
    upstream frontend {
        server 10.0.150.64:80;
    }

    upstream backend {
        server  10.0.133.168:80;
        server  10.0.143.115:80;
    }

    server {
        listen 80;
        server_name example.com;

        location / {
            proxy_pass http://frontend;
        }
    }

    server {
        listen 80;
        server_name api.example.com;

        location / {
            proxy_pass http://backend;
        }
    }
}


------------------------------


events {
#empty
}

http {
  
    server {
        listen 80;
     
        location / {
            proxy_pass http://frontend;
        }
    }
	
	  upstream frontend {
        server 10.0.152.223:80;
		server 10.0.150.152:80;
    }
	
	}

    -------------------------------------

    events {
    # empty placeholder
}


http {

    server {
        listen 80;

        location / {
            proxy_pass http://frontend;
        }

        location /api/ {
            rewrite ^/api/(.*)$ /$1 break;
            proxy_pass http://backend;
        }
    }

    upstream frontend {
        server client-service:80;
    }

    upstream backend {
        server api-service:5000;
    }
}

-------------------------

ssh -i sshkey.pem ubuntu@ip

chmod 400 sshkey.pem

corepack enable

yarn -v

pnpm -v

pnpm install

pnpm run dev

pnpm build

pnpm preview

pnpm preview --port 80

pnpm preview --host --port 80

curl ip

cd /etc/nginx

sudo nginx -t
sudo nginx -s reload

----------------------

Nginx-Laravel:
https://github.com/nathanaellsaraiva/example-app/blob/main/ec2-deploy.md


Nginx-Django:
https://wordspiner.xyz/deploy-a-django-application-on-ec2-instance-with-nginx/
