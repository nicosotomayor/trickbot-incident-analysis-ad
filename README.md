# Trickbot Incident Analysis in Active Directory

---

## SUMMARY

Se realizó el análisis de un incidente real de malware Trickbot en un entorno Active Directory a partir de tráfico de red (PCAP).

El análisis permitió identificar el host comprometido, reconstruir la cadena de ataque y confirmar el compromiso del Domain Controller.

---

## KEY RESULTS

- Host comprometido identificado mediante tráfico HTTP POST  
- Comunicación con servidores de comando y control (C2)  
- Exfiltración de credenciales en texto plano  
- Movimiento lateral hacia el Domain Controller  
- Malware distribuido como archivos disfrazados  
- Validación mediante VirusTotal  

---

## TECHNICAL FINDINGS

### Infected Host

- IP: 10.5.28.229  
- Hostname: CAT-BOMB-W7-PC  
- User: yas33  

---

### Command and Control

- 36.89.106.69  
- 203.176.135.102:8082  

---

### Compromised Credentials

- User: phillip.ghent  
- Password: gh3ntf@st  

---

### Lateral Movement

- User: jim734  
- Host: CATBOMBER-DC  

---

### Malware Artifacts

- cursor.png (PE32 executable)  
- imgpaper.png (PE32 executable)  

---

### SHA256 Hashes


4e76d73f3b303e481036ada80c2eeba8db2f306cbc9323748560843c80b2fed1
934c84524389ecfb3b1dfcb28f9697a2b52ea0ebcaa510469f0d2d9086bcc79a


---

## INCIDENT FLOW

1. Compromiso inicial del host  
2. Comunicación C2 mediante HTTP POST  
3. Exfiltración de credenciales  
4. Movimiento lateral al Domain Controller  
5. Entrega de malware  

---

## IMPACT

- Compromiso de credenciales  
- Acceso al Domain Controller  
- Riesgo de control total del dominio  
- Posible persistencia del atacante  

---

## EVIDENCE

### HTTP POST Traffic
![HTTP POST](screenshots/03_http_post_traffic_overview.png)

### Credentials Extraction
![Credentials](screenshots/05_credentials_extraction_strings.png)

### Malware Identification
![Malware](screenshots/08_malware_disguised_png.png)

### VirusTotal Validation
![VT1](screenshots/10_virustotal_cursor_analysis.png)
![VT2](screenshots/11_virustotal_imgpaper_analysis.png)

---

## DATASET

https://www.malware-traffic-analysis.net/2020/05/28/index.html  

El archivo PCAP no se incluye en este repositorio.

---

## AUTHOR

Nicolás Sotomayor  
SOC Analyst (Junior)

LinkedIn: https://linkedin.com/in/nikosotomayor-cyber  
GitHub: https://github.com/nicosotomayor  

---


