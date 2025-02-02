## Comparativa con Apache

*Vamos a ver una ligera comparativa entre los dos servidores:*

|                    | **Nginx**                               | **Apache**                                                          |
| ------------------ | --------------------------------------- | ------------------------------------------------------------------- |
| **Arquitectura**   | Basada en eventos (asincrónica).        | Basada en hilos o procesos.                                         |
| **Desempeño**      | Mejor manejo de conexiones simultáneas. | Puede volverse lento con muchas conexiones.                         |
| **Configuración**  | Archivos simples y modulares.           | Más compleja, aunque personalizable.<br>                            |
| **Caché**          | Integrada, optimizada para estáticos.   | Requiere módulos adicionales.<br>                                   |
| **Compatibilidad** | Orientado a alta concurrencia.          | Mejor para aplicaciones específicas con módulos personalizados.<br> |

*Nginx se prefiere en escenarios de alto tráfico, mientras que Apache es adecuado para entornos donde la personalización profunda es esencial.*
