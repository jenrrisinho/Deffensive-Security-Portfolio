# Defensive Security Portfolio

![Status](https://img.shields.io/badge/Status-Active_Project-success)
![Focus](https://img.shields.io/badge/Focus-Blue_Team_%7C_SOC_%7C_Threat_Detection-blue)
![Goal](https://img.shields.io/badge/Goal-10+_Labs-orange)

Bienvenido a mi repositorio técnico de seguridad defensiva.

Este repositorio funciona como un **laboratorio vivo y en constante evolución**. Aquí documento mis prácticas, hallazgos y metodologías aplicadas en retos de plataformas de práctica como TryHackMe y LetsDefend, con el objetivo de desarrollar una sólida base técnica en análisis de alertas, triage de incidentes, uso de SIEM y respuesta ante amenazas desde la perspectiva de un analista SOC.

## Sobre este proyecto y los Writeups

A diferencia de un repositorio estático, este es un proyecto en desarrollo. Las carpetas por plataforma (`TryHackMe/`, y a futuro `LetsDefend/`, etc.) contienen writeups de práctica personal continua, organizados por nivel de dificultad, y seguirán creciendo con nuevos retos.

La dificultad de cada reto de plataforma refleja la calificación oficial de origen:

- 🔵 **Very Easy**
- 🟢 **Easy**
- 🟡 **Medium**
- 🔴 **Hard**
- 🟣 **Insane**

## Aviso

Todas las prácticas se realizaron en entornos de simulación diseñados para entrenamiento de analistas SOC (simuladores de plataformas como TryHackMe y LetsDefend). Este material es exclusivamente educativo/académico.

## Tabla de Investigaciones

Los casos están divididos por sala/plataforma de origen.

### TryHackMe

Writeups de práctica personal en TryHackMe, organizados por dificultad. Este apartado se irá ampliando a medida que complete nuevas rooms.

| Room | Documento | Dificultad | Descripción breve | Herramientas |
|---|---|---|---|---|
| **Introduction to Phishing (SOC Simulator)** | `TryHackMe/Easy/Introduction-to-Phishing/Introduction_to_Phishing.md` | 🟢 Easy | Triage de 5 alertas de phishing en un simulador SOC, aplicando la metodología de las 5 Ws (Who, What, When, Where, Why) para diferenciar falsos positivos de verdaderos positivos, evaluación de escalación según impacto real (bloqueo por firewall vs. conexión permitida) y mapeo de la evidencia a técnicas MITRE ATT&CK. | Simulador SOC, TryDetectThis |
| **Payload (AI Supply Chain Security)** | `TryHackMe/Easy/Payload/Payload-TryHackMe.pdf` | 🟢 Easy | Investigación de un incidente de supply chain sobre un pipeline de ML: análisis de logs de despliegue, decompilación segura de un modelo pickle con backdoor (`os.system` vía beaconing HTTP) e inspección de un modelo `.h5` candidato con una capa `Lambda` maliciosa aún sin desplegar. | pickletools, fickling, modelscan, inspect_h5_model.py |
| **Snapped Phish-ing Line** | `TryHackMe/Easy/Snapped_Phish-ing_Line/Snapped_Phish-ing_Line-TryHackMe.pdf` | 🟢 Easy | Investigación de una campaña de phishing contra una empresa financiera: análisis de correos y de un adjunto HTML que redirige a un portal falso de Office 365, descarga y análisis de un phishing kit expuesto por *directory listing*, validación del hash SHA256 en VirusTotal, revisión del código PHP de exfiltración (`submit.php`), lectura de los logs de credenciales robadas y extracción de IOCs. | Thunderbird, sha256sum, VirusTotal, CyberChef |

*(Otras plataformas como LetsDefend se agregarán aquí a medida que se completen retos)*

## Herramientas y Recursos Utilizados

| Categoría | Nombre de la Herramienta | Enlace |
|---|---|---|
| **Frameworks de Referencia** | MITRE ATT&CK | <https://attack.mitre.org/> |
| **Metodología de Análisis** | 5 Ws (Who, What, When, Where, Why) | — |
| **SIEM** | Splunk | <https://www.splunk.com/> |
| **Verificación de URLs/IoCs** | TryDetectThis (simulador TryHackMe) | — |
| **Análisis de Modelos ML** | pickletools, fickling, modelscan | — |
| **Análisis de Correos** | Thunderbird | <https://www.thunderbird.net/> |
| **Inteligencia de Amenazas** | VirusTotal | <https://www.virustotal.com/> |
| **Decodificación y Transformación de Datos** | CyberChef | <https://gchq.github.io/CyberChef/> |
| **Análisis de Phishing Kits** | sha256sum, unzip, revisión manual de código PHP | — |

---

*Este repositorio se actualiza continuamente con nuevos informes y writeups técnicos de seguridad defensiva.*
