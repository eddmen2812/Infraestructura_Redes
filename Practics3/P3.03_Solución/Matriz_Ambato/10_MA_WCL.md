## Configuración WCL Gráfica
    #Configuración_WCL
    #Configuración del WCL-GRAFICA
    AdminUTJLM
    5An28x5i.
    System Name: WCL-UTJLM
    Managemet: 200.70.24.2
    SuNesk: 255.255.255.0
    Gateway: 200.70.24.2

    NetworkName: Docentes
    Security: WPA2-Personal
    Passphrase: Docentes@2023
    Confim Passphre: Docentes@2023 -->next

    --> next
    Apply

------------------------------------------
    #ingresar por web
    https://200.70.24.2

------------------------------------------

    #Habilitar en en perfil docentes-advance
    FlexConnect Local Switching 2	  Enabled
    FlexConnect Local Auth 12	  Enabled
--------------------------------------------
    #Crear un nuevo perfil
    Administrativos
    Administrativos
    #Habilitar 
    stauts: enable
    #Habilitar Wpa2
    #Hanilitar en security-administrativos
    WPA2 Policy:enable	
    WPA2 Encryption:enable
    PSk:Enable
    Contraseña: Administrativos@2023
    #Habilitar en en perfil administrativos-advance
    FlexConnect Local Switching 2	  Enabled
    FlexConnect Local Auth 12	  Enabled
-----------------------------------------------------
    #Crear un nuevo perfil
    Invitados
    Invitados
    #Habilitar 
    stauts: enable
    #Habilitar Wpa2
    #Hanilitar en security-invitados
    WPA2 Policy:enable	
    WPA2 Encryption:enable
    PSk:Enable
    Contraseña: Invitados@2023
    #Habilitar en en perfil administrativos-advance
    FlexConnect Local Switching 2	  Enabled
    FlexConnect Local Auth 12	  Enabled
------------------------------------------------------
    #server email
    hABILITAR RADIUS 
    habilitar el triple a
        creamos lo suarios y asignamos ip wcl
-------------------------------------------------------
    Ir a la contraladora
    security=new
    ponemos los parametros para la conexxcion
    Server Index (Priority)	1
    Server IP Address(Ipv4/Ipv6): 200.70.24.3
    Shared Secret Format
    Shared Secret: Radius@2023
    Confirm Shared Secret: Radius@2023
    Port Number: 1645
-------------------------------------------------------
    Ahora cambiamos la contrasñea con la lista del aaa
    Habilitados en security
    layer2
        802.1X: Enable
    aaa servers
        ponemos la ip y el puerto
    guardamos toda la configuración
-------------------------------------------------------
