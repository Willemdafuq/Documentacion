# TÍTULO DEL PROYECTO: ARQUITECTURA EMPRESARIAL EN AZURE.
## OBJETIVO DEL PROYECTO.

 Aplicar los conocimientos adquiridos durante el curso y familiarizarse con el uso de
herramientas 2.0 integradas en la plataforma Office 365 de Tajamar…

## TEMÁTICA DEL PROYECTO.

 Implementación de una arquitectura empresarial híbrida con despliegue de servicios en
Microsoft Azure.

## REQUISITOS DEL PROYECTO.

 La empresa MAT está planteando la migración de una parte de su arquitectura a Microsoft
Azure. Ha planificado desplegar en Azure las cargas de trabajo que requieren más recursos y mantener
on-premises los servicios más críticos para la seguridad:
La red de la empresa cuenta con un dominio mat.com implementado con dos controladores
de dominio on-premises para alta disponibilidad.

En el dominio on-premises hay 20 usuarios repartidos en 3 grupos:
- Sistemas:  3 usuarios
- Logística: 7 usuarios
- Desarrollo: 10 usuarios

# Ejercicio 1

Estos usuarios deben poder acceder a los recursos de Azure utilizando sus credenciales
on-premises. Los usuarios de sistemas deben tener acceso completo a todos los
recursos. Los usuarios de logística sólo deben tener permisos de lectura y los usuarios
de desarrollo sólo deben tener permisos de lectura y modificación sobre los recursos
relacionados con las aplicaciones web, pero no deben tener acceso al resto de
recursos. Cualquiera de los usuarios de los tres grupos debe poder resetear sus propias
contraseñas y estas deben sincronizarse en el directorio activo on-premises.

<p align="center">
<a><img src="https://i.imgur.com/nivlvkY.png" tittle="recurso" /></a>
</p>
