## Descripción Del Cliente Final  
* La Universidad Técnica Juan León Mera, en adelante UTJLM, es una universidad 
ubicada en el cantón Ambato.  
* En el campus existe el edificio administrativo que representará el principal punto de 
interconexión y único centro de operaciones. El edificio cuenta con 4 pisos, en los cuales 
será distribuido todo el personal, entre ellos administrativos, autoridades y el tercer piso 
está destinado al departamento de TI.  
* Junto con el nuevo campus de la UTJLM será incorporado un sistema informático de 
administración, gestión del sistema académico que demandará que el nuevo campus 
posea conectividad con los 4 edificios de las facultades de: Ingeniería, Ciencias de la 
Educación, Economía y negocios, y Ciencias de la Salud.  
* Las sedes Latacunga, Puyo, Tena y Alausí disponen de un edificio con 5 plantas cada 
uno.  
* En términos informáticos y tecnológicos hasta la fecha la UTJLM ha tenido pocos 
sistemas e infraestructura de conectividad y red, pero desean incorporar una nueva 
plataforma que les permita estar 100% conectadas a los recursos del edificio principal y 
las sedes
### Descripción de Requerimeintos
* El nuevo edificio central requiere de equipos de conectividad LAN para 30 puestos de 
trabajo. Para las autoridades académicas, cada puesto de trabajo se conectará con 1 
PC más 1 teléfono IP (6 usuarios matriz y 1 teléfono por cada sede). Adicionalmente, a 
los puestos de trabajo debe considerar conectividad para 4 impresoras de red (una por 
cada piso).  
* Conectividad wireless LAN para todo el campus, asumiendo que en cada piso se puede 
proveer de cobertura apropiada con puntos de acceso (AP) wireless. El acceso wireless 
debe ser provisto en alguna modalidad segura y debe considerar tres perfiles de usuario: 
docentes, estudiantes e invitados a través de la configuración de WLC.  
* Con la incorporación de los nuevos sistemas informáticos de administración y gestión 
se llegará a un total de 3 servidores (WEB, DNS, EMAIL, DHCP para IPv4, NTP y 
Aplicaciones), que se encuentran virtualizados. Toda la infraestructura deberá disponer de mecanismos de tolerancia a fallos (implementar RSTP y Etherchannel dentro del 
campus matriz)  
* Utilizar el direccionamiento IPv4 e IPv6 dependiendo de los servicios.  
* Implementar Vlan en IPv4 e IPv6 según su análisis (2 PCs por cada Vlan).  
* Para el servicio de VoIP utilizar el Call Manager Express a través del router 2811 con 
direccionamiento IPv4.  
* Para el proceso de enrutamiento IPv6/ IPv4 se utilizará el protocolo EIGRP (Tena y 
Puyo) y OSPF (Latacunga y Alausí) con enlaces redundantes y redistribución de rutas 
(router Ambato). Ambos protocolos deben ser configurados con proceso de 
autenticación.  
* Implementar las políticas de seguridad a través de 4 ACL dentro del campus 
universitario.  
* Implementar dispositivos en IoT gestionados por el dispositivo móvil. 
* No existe una idea clara de la implementación de un núcleo (core) en la red, pero se 
espera que la propuesta de la empresa (equipo de 2 estudiantes) oferente presente un 
diseño considerando la conectividad de infraestructura de todos los servicios, y la central 
telefonía IP entre la matriz y las sedes.  
* Respecto a la conectividad hacia internet, la UTJLM ya tiene acordado el servicio de 
acceso a internet con un ISP (CEDIA), el cual proveerá los enlaces de fibra óptica con 
1 Gbps entre las sedes y la matriz. El equipo CPE para el acceso a Internet es un router 
Cisco 4500 que está bajo la administración del ISP. Se deberá crear una ruta por defecto 
desde el router AMBATO para su conectividad a Internet. 
* La UTJLM está interesada en una solución de conectividad que les permita una 
capacidad de crecimiento, disponibilidad razonable, son conscientes que no cuentan 
con el recurso humano técnico calificado, por lo cual demandan una solución estable, 
tolerante a fallas y con facilidades de administración y mantenimiento.  
* Cualquier elección realizada debe estar alineada al 100% con los requerimientos de la 
UTJP