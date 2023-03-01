 
## Fix error Frontend

El error se debia a que faltaba un archivo de configuracion de react react-router. Por lo que para solucionar el error es necesario crear el archivo de cofiguracion a la ruta principal de react llamada nginx.conf para que nginx reconozca el archivo. El archivo debe contener lo siguiente para funcionar correctamente, habia que agregar los codigos de errro para que redirigiera a la pagina espesificada:

    server {
        listen       80;
        server_name  localhost;
        location / {
            root   /usr/share/nginx/html;
            index  index.html index.htm;
            try_files $uri /index.html;
        }
        error_page   500 502 503 504  /50x.html;
        location = /50x.html {
            root   /usr/share/nginx/html;
        }
    }

Y tambien debemos modificar lo siguiente nginx.Dockerfile del frontend:


    FROM nginx:1.22.1-alpine as runner
    COPY nginx.conf /etc/nginx/conf.d/default.conf
    COPY --from=compilacion /opt/app/build /usr/share/nginx/html
    EXPOSE 80
    CMD ["nginx", "-g", "daemon off;"]

Con esto el errro deberia estar solucionado correctamente.
