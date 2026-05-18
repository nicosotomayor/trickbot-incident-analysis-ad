Trickbot Incident Analysis – Active Directory Environment
Overview

Este proyecto documenta el análisis de un incidente real de malware Trickbot en un entorno Active Directory, a partir de tráfico de red (PCAP).

El objetivo fue identificar el host comprometido, reconstruir la cadena de ataque y extraer indicadores de compromiso (IoCs) utilizando herramientas de análisis de red.

Objectives
Identificar el host infectado
Detectar comunicación con infraestructura C2
Extraer credenciales comprometidas
Identificar movimiento lateral
Analizar artefactos maliciosos
Validar malware mediante inteligencia de amenazas
Tools Used
TShark (análisis de tráfico de red)
Wireshark (inspección visual)
Linux CLI (strings, file, sha256sum)
VirusTotal (validación de malware)
Scenario
Network Range: 10.5.28.0/24
Domain: catbomber.net
Domain Controller: 10.5.28.8 (CATBOMBER-DC)

Se analiza una infección Trickbot que logra propagarse hasta comprometer el Domain Controller.

Key Findings
Infected Host
IP: 10.5.28.229
Hostname: CAT-BOMB-W7-PC
User: yas33
Command and Control (C2)
36.89.106.69
203.176.135.102:8082
Compromised Credentials
User: phillip.ghent
Password: gh3ntf@st
Lateral Movement
User: jim734
Host: CATBOMBER-DC
Malware Artifacts
cursor.png (PE32 executable)
imgpaper.png (PE32 executable)
SHA256 Hashes
4e76d73f3b303e481036ada80c2eeba8db2f306cbc9323748560843c80b2fed1
934c84524389ecfb3b1dfcb28f9697a2b52ea0ebcaa510469f0d2d9086bcc79a
MITRE ATT&CK Techniques
T1071.001 – Command and Control over HTTP
T1003 – Credential Dumping
T1021 – Lateral Movement
T1041 – Exfiltration
T1036 – Masquerading
Analysis Evidence
HTTP POST Traffic

Credentials Extraction

Malware Identification

SHA256 Hash Calculation

VirusTotal Analysis




Incident Timeline
Initial infection of host 10.5.28.229
C2 communication via HTTP POST
Credential exfiltration (POP3)
Lateral movement to Domain Controller
Malware delivery via disguised executables
Impact Assessment
Compromise of user credentials
Access to Domain Controller
Potential full domain compromise
Risk of persistence and ransomware deployment
Recommendations
Aislar el host comprometido
Resetear credenciales
Auditar el Domain Controller
Bloquear direcciones IP maliciosas
Implementar monitoreo de red
Desplegar soluciones EDR
Project Structure
trickbot-incident-analysis-ad/
│
├── README.md
├── report/
│   └── Trickbot_Incident_Analysis_AD_2020-05-28.pdf
├── screenshots/
├── iocs/
│   └── iocs.txt
Dataset Source

Este análisis se basa en el siguiente caso:

https://www.malware-traffic-analysis.net/2020/05/28/index.html

El archivo PCAP no se incluye en este repositorio por razones de tamaño y propiedad del contenido.

Author

Nicolás Sotomayor
SOC Analyst (Junior)

LinkedIn: https://linkedin.com/in/nikosotomayor-cyber
GitHub: https://github.com/nicosotomayor

Final Note

Este proyecto demuestra la capacidad de analizar tráfico de red, investigar incidentes de seguridad y documentar hallazgos de forma profesional.
