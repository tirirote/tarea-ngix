## Casos prácticos

Verificamos la instalación de Nginx con el servicio instalado:

![image](https://github.com/user-attachments/assets/e55ebbdd-82ee-4de4-844c-9e9d07fa22c9)

Ahora modificamos la página web por defecto:

![image](https://github.com/user-attachments/assets/715ae7a9-c25c-4886-9d4f-2817cc557990)

Implementamos virtual hosting:

*Ahora implementaremos un servicio de hosting a través de NGINX, para poder alojar nuestras páginas webs.*

1. Crear los directorios para cada sitio:
2. 
![image](https://github.com/user-attachments/assets/6ee06323-8346-46eb-b763-91b6c739b50d)

3. Asignamos los permisos adecuados:
![image](https://github.com/user-attachments/assets/4f842761-2b30-4ee9-95dd-f1f97c9570e6)

4. Creamos los html para las webs de ejemplo:

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

6. Creamos los archivos de configuración para web2:

7. Habilitamos los sitios creando enlaces simbólicos:

8. Editar el archivo de hosts para pruebas locales:

9. Verificar la configuración de Nginx:

10. Reiniciamos el servicio de nginx:

```
sudo systemctl restart nginx
```

Autentificación, Autorización y Control de acceso
1. Identificar las interfaces de red:
2. Configurar el servidor para www.web1.org:
3. Configurar el servidor para www.web2.org:
4. Comprobamos la nueva configuración:
5. Reiniciamos el servicio de nginx:
6. Instalamos apache2-utils:
sudo apt install apache2-utils
7. Creamos el archivo de contraseñas:
sudo htpasswd -c /etc/nginx/.htpasswd usuario1
sudo htpasswd /etc/nginx/.htpasswd usuario 2

8. Creamos el directorio privado
9. Configuramos nginx para proteger el directorio /privado:
10. Verificar y recargar Nginx:
11. Comprobamos el acceso:
12. Modificamos la configuración de nginx para el dominio privado:
```
sudo nano /etc/nginx/sites-available/web1
```

13. Reiniciamos el servicio de nginx:
sudo nginx -t

14. Comprobamos:

Seguridad:
1. Instalamos certbot:
2. Configuramos Nginx para https:
3. Obtenemos un certificado con certbot:
4. Verificamos y probamos:








