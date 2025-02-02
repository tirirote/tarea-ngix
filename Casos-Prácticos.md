## Casos prácticos

Verificamos la instalación de Nginx con el servicio instalado:

![image](https://github.com/user-attachments/assets/e55ebbdd-82ee-4de4-844c-9e9d07fa22c9)

Ahora modificamos la página web por defecto:

![image](https://github.com/user-attachments/assets/715ae7a9-c25c-4886-9d4f-2817cc557990)

### Implementamos virtual hosting:

*Ahora implementaremos un servicio de hosting a través de NGINX, para poder alojar nuestras páginas webs.*

1. Crear los directorios para cada sitio:

![image](https://github.com/user-attachments/assets/6ee06323-8346-46eb-b763-91b6c739b50d)

2. Asignamos los permisos adecuados:
![image](https://github.com/user-attachments/assets/4f842761-2b30-4ee9-95dd-f1f97c9570e6)

3. Creamos los html para las webs de ejemplo:

Index de web1:

![image](https://github.com/user-attachments/assets/13b156e9-a932-4a56-a70c-ed2bb0b5910f)

Index de web2:

![image](https://github.com/user-attachments/assets/55eb20a1-ae5a-4947-bb82-8a28f8a6a687)

4. Configuramos los archivos de configuración nginx:

```
sudo nano /etc/nginx/sites-available/web1
```

![image](https://github.com/user-attachments/assets/82f4b41f-2ce4-43b4-a59b-8adfed36202d)


5. Creamos los archivos de configuración para web1:

```
sudo nano /etc/nginx/sites-available/web2
```

![image](https://github.com/user-attachments/assets/010056d7-a793-40d1-869c-1d272f73d772)

6. Creamos los archivos de configuración para web2

```
sudo ln -s /etc/nginx/sites-available/web1 /etc/nginx/sites-enables/
```

```
sudo ln -s /etc/nginx/sites-available/web2 /etc/nginx/sites-enables/
```

7. Habilitamos los sitios creando enlaces simbólicos:

```
suno nano /etc/hosts
```

8. Editar el archivo de hosts para pruebas locales:

```
sudo nano /etc/hosts
```

9. Verificar la configuración de Nginx:

```
sudo nginx -t
```

![image](https://github.com/user-attachments/assets/05624aa9-1bfb-4777-8450-b00086880c0d)

10. Reiniciamos el servicio de nginx:

```
sudo systemctl restart nginx
```

![image](https://github.com/user-attachments/assets/dfaeffc3-2bc8-4be7-85c8-f30e32744587)

![image](https://github.com/user-attachments/assets/3e5de94b-0c42-4ed0-a0ee-15e0d0be77b2)


### Autentificación, Autorización y Control de acceso

1. Identificar las interfaces de red.

```
ip addr show
```

![image](https://github.com/user-attachments/assets/6190f983-d642-419a-860e-50db1015c54e)

2. Configurar el servidor para www.web1.org.

```
sudo nano /etc/nginx/sites-available/web1
```

![image](https://github.com/user-attachments/assets/e00a7275-29df-44fe-807c-5841fbbd1976)

3. Configurar el servidor para www.web2.org.

```
sudo nano /etc/nginx/sites-available/web2
```

![image](https://github.com/user-attachments/assets/cf04e2da-4e79-4a5f-8896-b43b623f5e8b)


4. Comprobamos la nueva configuración.

```
sudo nginx -t
```

5. Reiniciamos el servicio de nginx

```
sudo systemctl restart nginx
```

6. Instalamos apache2-utils.

```
sudo apt install apache2-utils
```

7. Creamos el archivo de contraseñas.

```
sudo htpasswd -c /etc/nginx/.htpasswd usuario1
```

```
sudo htpasswd /etc/nginx/.htpasswd usuario 2
```

![image](https://github.com/user-attachments/assets/1e3201b6-6456-4c2b-b0a6-b60583c75a32)

8. Creamos el directorio privado.

````
sudo mkdir /var/www/web1/privado
````

````
sudo chmod -R 755 7var/www/web1
````

9. Configuramos nginx para proteger el directorio /privado.

```
sudo nano /etc/nginx/sites-available/web1
```
![image](https://github.com/user-attachments/assets/62b2d220-3416-445e-8bfb-fd851eaf65f2)

10. Verificar y recargar Nginx.

```
sudo nginx -t
```

```
sudo systemctl reload nginx
```

11. Comprobamos el acceso.

![image](https://github.com/user-attachments/assets/08982891-3adb-41f1-9d47-c80b9f79c009)

12. Modificamos la configuración de nginx para el dominio privado.

```
sudo nano /etc/nginx/sites-available/web1
```

![image](https://github.com/user-attachments/assets/37f7ee32-5703-4240-aeb0-c26e2e7f2c6e)

13. Reiniciamos el servicio de nginx.

```
sudo nginx -t
```

```
sudo systemctl restart nginx
```

### Seguridad.

1. Instalamos certbot:

````
sudo apt update
````

````
sudo apt install cerbot python3-certbot-nginx
````

2. Configuramos Nginx para https:

````
sudo ls /etc/nginx/sites-enables
````

````
sudo nginx -t
````

3. Obtenemos un certificado con certbot:

````
sudo certbot --nginx -d www.web1.org
````

4. Verificamos y probamos:

````
sudo nginx -t
````

````
sudo systemctl restart nginx
````
