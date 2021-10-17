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
- Windows con 10.0.2.11/8

## Ejecución de escaner de red Nmap

Con esta herramienta descubriremos puertos y servicios abiertos en la máquina objetivo.
