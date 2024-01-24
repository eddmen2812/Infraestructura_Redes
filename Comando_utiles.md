### Comandos de Configuración
|Comando|	Descripcion|	Nota|
|--------|------------|----------|
|enable	|Acceso al modo privilegio/modo enable	||
|configure terminal| 	Ingreso al modo de configuracion global||	Configuracion general del equipo|
|hostname	|Asignar un nombre al equipo||
|no ip domain-lookup|	No realice busquedas DNS||
|ip domain-name|	Definir un nombre de dominio al equipo||
|cryto key generate rsa general-key modulus 1000	|Definir una clave de encriptacion||
|username cisco secret cisco	|Definir un usuario y clave para ingresar al equipo|	
|username cisco privilege 15 secret cisco|Definir un usuario y clave para ingresar al equipo||
|banner modt#SOLO PERSONAL AUTORIZADO#	|Mensaje de Ingreso al Equipo	||
|enable secret CISCO|	Proteccion de Acceso al Modo Privilerio	||
|line console 0	|Ingreso a la linea de consola||
|password CISCO login|	Configura contraseña de ingreso	|Configuracion Básica|
|login local	|Configura contraseña de ingreso	||
|exec-timeout 10 10|	||
|line vty 0 15|||
|transport input ssh	|Activar el servicio ssh	||
|service password-encryption 	|Encripta las contraseñas en texto plano en el equipo|
||security passwords min-length 8|	Configura el tamaño minimo de las constraseñas||
|login block-for 120 attempts 3 within 60|	Bloquea acceso al equipo por 120s   cuando se realizan 3 intentos fallidos  dentro de 60s	||
#### Router
| Comando | Descripición |
| --------- | -------- |
| interface G0/0/0 | Define la interfaz |
|ip address 192.168.1.1 255.255.255.0|Definir una direccion IP en la interface|
|no shutdown	|Activar interface|
|Description    ENLACE-R1-R2	|Define un descripcion  de la interface. "Usado para definir la señal de reloj en la comucacion en enlaces seriales|
|clock rate 64000|Debe ser colocado en el DCE"|
|ipv6 unicast-routing|	Habilita ipv6 en el equipo	|
|interface G0/0/0|	Define la interfaz|	
|ipv6 address 2001:ab:cd:0001::1/64|	Definir una direccion IP en la interface	|
|ipv6 address fe90::1 link-local	|Definir una direccion IP  de enlace local en la interface	|
|no shutdown	|Activar interface	|
|Description    ENLACE-R1-R2|	Define un descripcion  de la interface	|
|ipv6 route ::/0 2001:ab:cd:0001::1	|Define ruta estatica en ipv6|
|clock rate 64000|	"Usado para definir la señal de reloj en la comucacion en enlaces seriales. Debe ser colocado en el DCE"|
		
### Switch		

| Comando | Descripición |
| --------- | -------- |
|Interface G0/0/||
|speed	|Negocia  el AB en la interface 10/100/1000       auto	|
|duplex	Negocia la comunicación en half-duplex/full-duplex      auto	|
|mdix auto	|Negocia la configuracion del cable de cobre directo-cruzado|
|interface vlan 1	|Define la interfaz virtual para acceder a la adminisytracion del equipo	|
|ip address 192.168.1.1 255.255.255.0	|Definir una direccion IP en la interface|	
|no shudown	|Activar interface|	
|Description   VLAN-ADMINISTRACION	|Define un descripcion  de la interface	|
|ip default-gateway 192.168.1.1	|Define un gateway para acceso desde otras redes	|
|interface vlan 1|Define la interfaz virtual para acceder a la adminisytracion del equipo	|
|ipv6 address 2001:ab:cd:0001::1/64| Definir una direccion IP en la interface	|
|ipv6 address fe90::1 link-local	|Definir una direccion IP  de enlace local en la interface|
|no shutdown|	Activar interface	|
|Description   VLAN-ADMINISTRACION	|Define un descripcion  de la interface	|
|ipv6 route ::/0 2001:ab:cd:0001::1	|Define ruta estatica en ipv6|
### Comando para ver
| Comando | Descripición |
| --------- | -------- |
|do COMANDO show|	Ejecuta un comando del mode enable dentro del modo de configuracion	|
|enable	|Acceso al modo privilegio/modo enable	|
|show running-config   / show run|	Vizualiza la configuracion  en ejecución/ Equipo Activo	|
|show startup-config | 	Vizualiza la configuracion  guardada en el equipo/ NVRAM	|
|copy running-config  startup-config  / copy run start	|Guardar la configuracion de Ejecucion	|
|write    / wr	|Guardar la configuracion de Ejecucion	|
|erase startup-config|	Borrar la configuracion guardada en el equipo	|
|reload |	Reiniciar el equipo	|
|ping |	Utilidad para realizar test de conectividad| 	
|debug /undebug all	|Vizualiza eventos en el equipo	|
|terminal monitor	|Vizualiza mensajes de eventos en el equipo	|
|show ip interface brief   / sh ip int br	|Muestra el estado de las interfaces resumido	|
|show ip arp 	|Muestra la tabla MAC en capa 3	|
|show ip route	|Muestra la tabla de rutas	|
|show ip interface |	Muestra estado de las interfaces en capa 3|	
|show interface 	|Muestra el estado de las interfaces individual	|
|show version	|Muestra las caracteristicas del equipo	|
|how ipv6 interface brief   / sh ipv6 int br	|Muestra el estado de las interfaces resumido	|
|show ipv6 route	|Muestra la tabla de rutas	|
|show ipv6  interface 	|Muestra estado de las interfaces en capa 3	|
|show cdp neighbors	|Muestra equipos cisco directamente conectados	|
|show mac-address-table	|Vizualizar la tabla de direcciones MAC o tabla CAM del switch	|

### Comando en PC	
| Comando | Descripición |
| --------- | -------- |
|ping |	Utilidad para realizar test de conectividad 	|
|tracert	|Muestra un trazado de ruta	|
|ipconfig /displaydns	|Vizualiza cable dns	|
|ipconfig /all       ipconfig /release     ipconfig /renew	|Vizualizar los parametros de configuarcion del PC	|
|arp -a	|Vizualizar la tabla ARP,    IP  ---------> MAC (?)	|
|route print	|Vizualiza tabla de rutas en PC Windows 	|
|nslookup	|Muestra la resolucion Nombre -Direccion	|
|netstat -r	|Muestra conexiones activas	|
### Otros comandos de PACKET TRACERT
| Comando | Descripición |
| --------- | -------- |
|ssh - l  username direccionIP	|Acceso Remoto  a los equipos CISCO	|
|telnet |Accesos Directos		|
### Comandos de acceso directo
| Comando | Descripición |
| --------- | -------- |
|Ctrol A	|Desplazarnos al incio de la linea	|
|Ctrol E|	Desplazarnos al incio de la linea	|
|TAB	Completar un comando	|
|Backspace	|Borrar un carácter a la izquierda	|
|Teclas de movimiento  arriba-abajo	|Vizualizar el historial de comandos ingresados	|
|Teclas de movimiento derecha - izquierda|	Desplazarnos en la linea de comandos	|
