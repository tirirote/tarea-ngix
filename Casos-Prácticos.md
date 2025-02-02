Verificamos la instalación de Nginx con el servicio instalado
Ahora modificamos la página web por defecto
Implementamos virtual hosting
1. Crear los directorios para cada sitio:
2. Asignamos los permisos adecuados:
3. Creamos los html para las webs de ejemplo:
4. Configuramos los archivos de configuración nginx:
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








