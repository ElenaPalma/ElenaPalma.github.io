# Nombres de chats incorrectos en Whatsapp (Android) 

El problema se dio al intentar restaurar a la copia de seguridad en un teléfono nuevo con Android 15.

Específicamente, se restauraban los chats y los archivos multimedia, pero los nombres estaban mezclados, es decir que eran nombres que si tenia en los contactos de Google, pero no eran los nombres correctos.

## Descripción del error
El problema persistió aún después de seguir las recomendaciones en la [página de Soporte de Whatsapp.](https://faq.whatsapp.com/522615322631338/?helpref=uf_share)
- Borré la caché de Whatsapp y Actualicé los contactos.
  -  Reinicié el teléfono e intenté de nuevo.
- Intenté desinstalando Whatsapp y restaurando de nuevo.
   
 ==================
 - Volví a iniciar sesion en Whatsapp en el telefono anterior, donde parecia que el problema de los nombres se había solucionado.
 - Después de este punto, intenté hacer una transferencia de chat (leyendo el QR para no tener que cargar la copia de seguridad de Google, en caso de que el backup estuviera corrupto), el cual falló aunque lo intenté varias veces.
 - Intenté hacer una nueva copia de seguridad con los nombres corregidos, y también falló.
 - Al reiniciar el teléfono anterior, los nombres cargaron incorrectos también.
 
 **Otros puntos**

 - Los contactos en mi aplicación de Agenda si estaban correctos y estaban guardados en mi cuenta de Google.
 - Whatsapp tenía permiso para acceder a mis contactos.
 - La copia de seguridad que se estaba restaurando si era la de la misma cuenta de Google en donde habia hecho la copia en el telefono anterior, y donde había verificado que los contactos estuvieran recientemente sincronizados. 
 - En mi teléfono anterior tenía varias cuentas de Google en donde había diferentes contactos guardados.
   
 *Como nota, desinstalé y reinstalé Whatsapp múltiples veces después de cada cambio que hice, también repetí la eliminación de caché y actualización de contactos.*


## Mi solución

### ⬅️ En el teléfono anterior
### 1. Desactivar guardar contactos en cuenta de Whatsapp.

Ir a **Nuevo chat** > **Ajustes (tres puntos verticales)** > **Configuración de contactos**  > **Desactivar Contactos de Whatsapp.**

Al desactivarlo, pude ver los nombres en los chats correctamente de nuevo. 

### 2. Juntar a todos los contactos en una sola cuenta donde haré la copia de seguridad. 

Esto se puede hacer por la [página Web Contacts](https://contacts.google.com/) o por medio de la app de Contactos en Android. 

**Si es por medio de la página Web**

Se pueden seleccionar todos los contactos que se quieren transferir y exportarlos a un csv. Después de tener el archivo, acceder con la nueva cuenta e importarlos. 

Finalmente, se pueden deben eliminar de la cuenta anterior. 

*El objetivo es que no haya duplicacion de contactos y todos se encuentren en un solo lugar* 

**Si es por medio de la app**

En mi version de la app de Contactos, se pueden filtrar por la cuenta de Google en donde estan guardados. Así que primero los filtré, luego los seleccioné todos y, en el menú, seleccionar "Transferir a otra cuenta" en donde estará la copia de seguridad. 

[Guía para ambos procesos](https://www.technipages.com/transfer-contacts-gmail-account/)

### 3. Asegurarse de que el total de contactos ya se encuentra en una sola cuenta y el resto de las cuentas no tiene contactos guardados. 

Después, en las configuraciones del teléfono, forzar una sincronización de las cuentas de Google de donde se borraron y a donde se transfirieron los contactos, para que la información esté actualizada en todos lados. 

### 4. Forzar un Back up 

En Whatsapp, ir a las **Configuraciones**  > **Chats**  > **Backup** 

‼️Ultra verificar que se haga backup en la cuenta correcta, donde se guardaron todos los contactos. 

Puede tomar bastante tiempo, dependiendo de los archivos y fotos que haya en las conversaciones. 

Dejarlo trabajar por si solo hasta que ya haya terminado de guardar el backup.

Personalmente, cambie las configuraciones del teléfono para que la pantalla no se apagara y poder ver que el proceso va de 0% a 100% y estar completamente segura de que la hora del último Backup sea el que acabo de hacer.

### ➡️ En el teléfono nuevo
### 5. Limpiar caché de Whatsapp 

En las configuraciones del teléfono, buscar Apps y ubicar Whatsapp. 

Aquí, dependiendo de la versión de Android puede variar, pero generalmente "Borrar Cache" se encuentra al final de las especificaciones de la aplicación, en este caso, Whatsapp. 

También es posible que se encuentre dentro del apartado de "Almacenamiento" en las especificaciones de la aplicación. 
### 6. Desinstalar y reinstalar Whatsapp. 
### 7. Eliminar del teléfono las cuentas "extras" de Google y dejar solamente la que tiene la copia de seguridad.
### 8. Empezar la configuración inicial de Whatsapp y restaurar los contactos y chats desde la copia de seguridad. 

## Conclusión 

Esos fueron los pasos que seguí para solucionar mi problema, desconozco cual fue el origen pero puede haber sido una copia de seguridad corrupta o algun problema al sincronizar los chats con los contactos, teniendo contactos en diferentes cuentas de Google. 
Después de eso, volví a agregar las cuentas "extras" de Google al teléfono. 


Suerte 🥲
