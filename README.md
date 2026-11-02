# Defensive Security Portfolio

![Status](https://img.shields.io/badge/Status-Active_Project-success)
![Focus](https://img.shields.io/badge/Focus-Blue_Team_%7C_SOC_%7C_Threat_Detection-blue)
![Goal](https://img.shields.io/badge/Goal-10+_Labs-orange)

Bienvenido a mi repositorio técnico de seguridad defensiva.

Este repositorio funciona como un **laboratorio vivo y en constante evolución**. Aquí documento mis prácticas, hallazgos y metodologías aplicadas en retos de plataformas de práctica como TryHackMe, CyberDefenders y LetsDefend, con el objetivo de desarrollar una sólida base técnica en análisis de alertas, triage de incidentes, uso de SIEM y respuesta ante amenazas desde la perspectiva de un analista SOC.

## Sobre este proyecto y los Writeups

A diferencia de un repositorio estático, este es un proyecto en desarrollo. Las carpetas por plataforma (`TryHackMe/`, `CyberDefenders/`, y a futuro `LetsDefend/`, etc.) contienen writeups de práctica personal continua, organizados por nivel de dificultad, y seguirán creciendo con nuevos retos.

La dificultad de cada reto de plataforma refleja la calificación oficial de origen:

- 🔵 **Very Easy**
- 🟢 **Easy**
- 🟡 **Medium**
- 🔴 **Hard**
- 🟣 **Insane**

## Aviso

Todas las prácticas se realizaron en entornos de simulación diseñados para entrenamiento de analistas SOC (simuladores de plataformas como TryHackMe y LetsDefend). Este material es exclusivamente educativo/académico.

Los writeups de CyberDefenders priorizan el método y la orientación: omiten las respuestas directas y difuminan los valores sensibles en las capturas, para respetar las políticas de la plataforma y no arruinar el reto a otros usuarios.

## Tabla de Investigaciones

Los casos están divididos por sala/plataforma de origen.

### TryHackMe

Writeups de práctica personal en [TryHackMe](https://tryhackme.com/), organizados por dificultad. Este apartado se irá ampliando a medida que complete nuevas rooms.

| Room | Documento | Dificultad | Descripción breve | Herramientas |
|---|---|---|---|---|
| **Introduction to Phishing (SOC Simulator)** | [Introduction to Phishing.md](SOC-Simulator-TryHackMe/Easy/Introduction%20to%20Phishing/Introduction%20to%20Phishing.md) | 🟢 Easy | Triage de 5 alertas de phishing en un simulador SOC con la metodología 5 Ws, diferenciando falsos y verdaderos positivos según impacto real y mapeando la evidencia a MITRE ATT&CK. | Simulador SOC, TryDetectThis |
| **Payload (AI Supply Chain Security)** | [Payload-TryHackMe.pdf](TryHackMe/Easy/Payload/Payload-TryHackMe.pdf) | 🟢 Easy | Incidente de supply chain en un pipeline de ML: decompilación de un modelo pickle con backdoor (`os.system` vía beaconing HTTP) e inspección de un `.h5` con capa `Lambda` maliciosa sin desplegar. | pickletools, fickling, modelscan, inspect_h5_model.py |
| **Snapped Phish-ing Line** | [Snapped_Phish-ing_Line-TryHackMe.pdf](TryHackMe/Easy/Snapped_Phish-ing_Line/Snapped_Phish-ing_Line-TryHackMe.pdf) | 🟢 Easy | Campaña de phishing contra una empresa financiera: análisis de un adjunto HTML falso de Office 365, phishing kit expuesto por *directory listing*, validación en VirusTotal y extracción de IOCs. | Thunderbird, sha256sum, VirusTotal, CyberChef |
| **Portal Drop** | [Portal_Drop-TryHackMe.pdf](TryHackMe/Easy/Portal_Drop/Portal_Drop-TryHackMe.pdf) | 🟢 Easy | Intrusión al CRM de TryPatchMe: correlación de logs y EDR para reconstruir brute force, subida de web shell (`invoice.php`), reverse shell como `www-data` y exfiltración de BD (MITRE T1505.003). | grep, CyberChef, EDR/XDR Console |
| **Phishing Books** | [Phishing_Books-TryHackMe.pdf](TryHackMe/Easy/Phishing_Books/Phishing_Books-TryHackMe.pdf) | 🟢 Easy | Análisis forense de un correo de phishing con typosquatting en el remitente, deofuscación de un HTML malicioso, cadena de redirección con IDN homograph attack y atribución al threat actor Cobalt Dickens / Silent Librarian. | Thunderbird, CyberChef, TryDetectThis |
| **Mr. Phisher** | [MrPhisher-TryHackMe.pdf](TryHackMe/Easy/MrPhisher/MrPhisher-TryHackMe.pdf) | 🟢 Easy | Ingeniería inversa de un documento malicioso habilitado para macros: extracción e inspección estática de código de evasión en VBA y desofuscación de un algoritmo binario XOR dinámico basado en índices. | LibreOffice Basic, Editor de Macros VBA |

### CyberDefenders

Writeups de Blue Team CTF Challenges de [CyberDefenders](https://cyberdefenders.org/), organizados por dificultad. Este apartado se irá ampliando a medida que complete nuevas rooms.
| Reto | Documento | Dificultad | Descripción breve | Herramientas |
|---|---|---|---|---|
| **[JetBrains](https://cyberdefenders.org/blueteam-ctf-challenges/jetbrains/)** | [JetBrains-CyberDefenders.pdf](CyberDefenders/Easy/JetBrains/JetBrains-CyberDefenders.pdf) | 🟢 Easy | Network Forensics: análisis de una captura de tráfico de un servidor TeamCity comprometido para reconstruir la cadena de ataque (acceso inicial, webshell, ejecución de comandos y escape al host) y mapear las técnicas a MITRE ATT&CK. | Wireshark, MITRE ATT&CK |
| **[RetailBreach](https://cyberdefenders.org/blueteam-ctf-challenges/retailbreach/)** | [RetailBreach-CyberDefenders.pdf](CyberDefenders/Easy/RetailBreach/RetailBreach-CyberDefenders.pdf) | 🟢 Easy | Network Forensics: análisis de una captura de tráfico de una tienda en línea comprometida, desde el reconocimiento con fuerza bruta de directorios hasta el robo de sesión de un administrador vía XSS almacenado y explotación de un path traversal. | Wireshark |

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
| **Análisis de Tráfico de Red** | Wireshark, NetworkMiner | <https://www.wireshark.org/> / <https://www.netresec.com/?page=NetworkMiner> |
| **Análisis de Phishing Kits** | sha256sum, unzip, revisión manual de código PHP | — |
| **Análisis de Logs Web** | grep / awk | — |
| **EDR/XDR** | TryDetectMe XDR (simulador TryHackMe) | — |

---

*Este repositorio se actualiza continuamente con nuevos informes y writeups técnicos de seguridad defensiva.*
