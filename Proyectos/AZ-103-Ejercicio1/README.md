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

Desde el portal de Azure, en el Tenant de Azure Mad.com nos descargamos Azure AD Connect y lo instalamos en nuestra maquina On-premises

<p align="center">
<a><img src="https://i.imgur.com/nivlvkY.png" tittle="recurso" /></a>
</p>

<p align="center">
<a><img src="https://i.imgur.com/c75IGU8.png" tittle="recurso" /></a>
</p>

Utilizamos Password Hash Synchronization porque es el único que nos permite habilitar Password Writeback y en el ejercicio se nos pide sincronizar entre el directorio de Azure y el directorio On-premises.

<p align="center">
<a><img src="https://i.imgur.com/DRMmWp9.png" tittle="recurso" /></a>
</p>

Nos pedirá un usuario de Azure, así que creamos uno que tenga permisos de administrador global dentro del tenant.

<p align="center">
<a><img src="https://i.imgur.com/v9N06aq.png" tittle="recurso" /></a>
</p>

<p align="center">
<a><img src="https://i.imgur.com/v9N06aq.png" tittle="recurso" /></a>
</p>

Despues de identificarnos con el usuario nos aparece el dominio local mat.com ,nos pedirá una cuenta de AD que tenga los permisos necesarios para poder hacer la sincronización periodica, asi que le ponemos la cuenta del administrador local.

<p align="center">
<a><img src="https://i.imgur.com/dTj4ZyO.png" tittle="recurso" /></a>
</p>

Utilizamos la cuenta de administrador del dominio (Enterprise).

<p align="center">
<a><img src="https://i.imgur.com/XYKtONF.png" tittle="recurso" /></a>
</p>

<p align="center">
<a><img src="https://i.imgur.com/yCBYZTQ.png" tittle="recurso" /></a>
</p>

Ahora tenemos que añadir el UPN en la maquina On-premises DC-1, para los usuarios de madt38w06.

<p align="center">
<a><img src="https://i.imgur.com/J3uniTI.png" tittle="recurso" /></a>
</p>

Ahora todos los usuario tendrán el UPN alternativo.

<p align="center">
<a><img src="https://i.imgur.com/EFF7Bnb.png" tittle="recurso" /></a>
</p>

Refrescamos y vemos que ya nos aparece el UPN que hemos creado.

<p align="center">
<a><img src="https://i.imgur.com/z6yvrgL.png" tittle="recurso" /></a>
</p>
