# Implementación de Suricata como IDS en Homelab

Proyecto personal de ciberseguridad defensiva orientado al despliegue de Suricata como IDS (Intrusion Detection System) en un entorno homelab, con el objetivo de monitorear tráfico de red, crear reglas personalizadas y validar alertas a partir de tráfico malicioso simulado.

## Descripción del proyecto

Este laboratorio fue desarrollado en un entorno doméstico controlado con fines de aprendizaje práctico en Blue Team y monitoreo de seguridad de red.

La implementación se realizó sobre Parrot OS utilizando Suricata 7.0.10 en modo IDS, escuchando sobre la interfaz br0 dentro de la red local 192.168.1.0/24. Como máquina atacante se utilizó una VM Kali Linux, encargada de generar tráfico de prueba para validar el funcionamiento del sistema de detección.

Además del despliegue base de Suricata, el proyecto incluyó la creación de reglas personalizadas, el ajuste de parámetros clave en `suricata.yaml`, la configuración persistente del bridge de red y la verificación de alertas generadas en los archivos `fast.log` y `eve.json`.

## Objetivos

- Implementar Suricata como IDS en un entorno homelab.
- Configurar correctamente la red y la interfaz de monitoreo.
- Crear reglas personalizadas para detección de actividad sospechosa.
- Simular tráfico malicioso desde un entorno atacante controlado.
- Validar alertas generadas y documentar los resultados.

## Arquitectura del laboratorio

El laboratorio está compuesto por dos sistemas dentro de la misma red local:

- Parrot OS como sensor IDS  
  - IP: `192.168.1.76`
  - Rol: ejecución de Suricata en modo IDS
  - Interfaz monitoreada: `br0`

- Kali Linux como máquina atacante  
  - IP: `192.168.1.101`
  - Rol: generación de tráfico de prueba y simulación de ataques

## Casos de detección implementados

Se diseñaron y validaron reglas personalizadas para detectar:

- **ICMP Echo Request / Ping Sweep**
- **Escaneo TCP SYN con Nmap**
- **Fuerza bruta SSH**

Estas detecciones fueron mapeadas a técnicas de MITRE ATT&CK:

- `T1018` – Remote System Discovery
- `T1046` – Network Service Scanning
- `T1110` – Brute Force

## Validación y resultados

Las pruebas realizadas permitieron verificar que Suricata detecta correctamente el tráfico generado desde Kali Linux y registra las alertas esperadas en:

- `fast.log`
- `eve.json`

El proyecto documenta tanto la configuración como la evidencia de funcionamiento de cada regla, mostrando el flujo completo desde la generación del tráfico hasta la alerta final.

## Contenido del repositorio

Este repositorio incluye la documentación completa del proyecto en formato PDF:

- [Ver documentación completa](./suricata-documentacion.pdf)

## Tecnologías utilizadas

- Suricata 7.0.10
- Parrot OS
- Kali Linux
- VirtualBox
- Linux Networking / Bridge
- MITRE ATT&CK
- IDS / Network Security Monitoring

## Autora
Daniela H.
