# Guide de Publication LinkedIn : Projet Wazuh SIEM/SOAR

Ce document contient le texte prêt à l'emploi (en français et en anglais) pour votre publication LinkedIn, ainsi que les références vers les 5 diapositives (slides) générées pour votre carrousel.

---

## 📁 Vos Visuels LinkedIn (Carrousel)

Vous avez désormais **deux styles de carrousel** prêts sur votre Bureau. Choisissez celui qui convient le mieux à vos préférences :

### Option A : Style Sombre (Cyberpunk / High-Tech)
Les images sont situées dans : `/home/ae6/Desktop/WazuhSIEM_LinkedIn_Assets/`
1. **Slide 1 : Cover** -> [Slide1_Cover.jpg](file:///home/ae6/Desktop/WazuhSIEM_LinkedIn_Assets/Slide1_Cover.jpg)
2. **Slide 2 : Architecture** -> [Slide2_Architecture.jpg](file:///home/ae6/Desktop/WazuhSIEM_LinkedIn_Assets/Slide2_Architecture.jpg)
3. **Slide 3 : Détection** -> [Slide3_Detection.jpg](file:///home/ae6/Desktop/WazuhSIEM_LinkedIn_Assets/Slide3_Detection.jpg)
4. **Slide 4 : SOAR Réponse Active** -> [Slide4_ActiveResponse.jpg](file:///home/ae6/Desktop/WazuhSIEM_LinkedIn_Assets/Slide4_ActiveResponse.jpg)
5. **Slide 5 : Zero Trust & SCA** -> [Slide5_Compliance.jpg](file:///home/ae6/Desktop/WazuhSIEM_LinkedIn_Assets/Slide5_Compliance.jpg)

### Option B : Style Clair (Rapport Académique, Corporate & Linux)
Les images sont situées dans : `/home/ae6/Desktop/WazuhSIEM_LinkedIn_Assets_Light/`
1. **Slide 1 : Cover** -> [Slide1_Cover.jpg](file:///home/ae6/Desktop/WazuhSIEM_LinkedIn_Assets_Light/Slide1_Cover.jpg)
2. **Slide 2 : Architecture** -> [Slide2_Architecture.jpg](file:///home/ae6/Desktop/WazuhSIEM_LinkedIn_Assets_Light/Slide2_Architecture.jpg)
3. **Slide 3 : Détection (Terminaux)** -> [Slide3_Detection.jpg](file:///home/ae6/Desktop/WazuhSIEM_LinkedIn_Assets_Light/Slide3_Detection.jpg)
4. **Slide 4 : SOAR Réponse Active** -> [Slide4_ActiveResponse.jpg](file:///home/ae6/Desktop/WazuhSIEM_LinkedIn_Assets_Light/Slide4_ActiveResponse.jpg)
5. **Slide 5 : Zero Trust & SCA** -> [Slide5_Compliance.jpg](file:///home/ae6/Desktop/WazuhSIEM_LinkedIn_Assets_Light/Slide5_Compliance.jpg)

---

## ✍️ Version Française (Recommandée pour vos recruteurs locaux)

**Copiez-collez le texte ci-dessous pour votre post :**

***

🚀 **Comment réduire le temps de remédiation d'une cyberattaque de plusieurs heures à quelques millisecondes ?**

Je viens de finaliser la mise en place d'un laboratoire de sécurité complet axé sur le déploiement d'un **SOC/SIEM** avec **Wazuh** et l'automatisation de la réponse aux incidents (**SOAR**). 

Ce projet pratique simule une posture de **Défense en Profondeur** à travers trois grandes phases clés :

1️⃣ **Phase 1 : Attaque passive & Détection SSH** 
* Simulation d'une intrusion via scan de ports (Nmap) et attaque par dictionnaire (Hydra) contre le service SSH d'un serveur cible Ubuntu.
* Corrélation et centralisation des logs dans le manager Wazuh (Règle critique 5763 de niveau 10).

2️⃣ **Phase 2 : Défense Active (SOAR)**
* Configuration du module `active-response` sur le serveur Wazuh Manager et l'agent cible.
* Déclenchement automatique d'un script de pare-feu (`firewall-drop`) bloquant l'adresse IP de l'attaquant en moins d'une seconde, coupant net toute tentative d'intrusion.

3️⃣ **Phase 3 : Post-Exploitation & Zero Trust**
* Audit comportemental interne avec la détection de tentatives d'élévation de privilèges locaux (abris de `sudo` simulé avec un utilisateur restreint).
* Évaluation continue de la configuration système (SCA) alignée sur les standards **CIS Benchmarks** et surveillance de l'intégrité des fichiers sensibles (FIM).

Ce projet m'a permis de valider des compétences clés en administration Linux durcie, configuration de pare-feu, gestion de logs centralisée et détection de menaces en temps réel.

👉 Le rapport complet du projet est disponible en format PDF sur mon portfolio.

Quelles sont vos solutions SIEM/SOAR open-source préférées pour sécuriser des infrastructures d'entreprise à budget optimisé ?

#Cybersécurité #SIEM #SOAR #Wazuh #ThreatHunting #BlueTeam #SOC #ZeroTrust #SecOps #CISBenchmarks #Linuxmint #Ubuntu

***

---

## ✍️ Version Anglaise (Idéale pour une portée internationale)

**Copiez-collez le texte ci-dessous pour votre post :**

***

🚀 **How do you reduce the containment time of a network attack from hours to milliseconds?**

I just completed the deployment of a full **SOC/SIEM** laboratory centered on **Wazuh** and Automated Incident Response (**SOAR**).

This practical lab simulates a **Defense-in-Depth** strategy broken down into three key execution phases:

1️⃣ **Phase 1: Passive Threat Detection**
* Simulated external reconnaissance using Nmap and a dictionary-based SSH brute force attack using Hydra against a target Ubuntu host.
* Correlated authentication logs inside the Wazuh Manager, triggering critical Alert Rule 5763 (Level 10).

2️⃣ **Phase 2: Active Defense (SOAR)**
* Configured the `active-response` module on the manager and target agent.
* Automated network blocking using a built-in `firewall-drop` script, dropping the attacker's IP on the local firewall within milliseconds of detection.

3️⃣ **Phase 3: Post-Exploitation & Zero Trust Audits**
* Simulated an insider threat scenario by auditing unauthorized local privilege escalation attempts (`sudo` abuse).
* Enforced OS hardening configuration assessments (SCA) aligned with **CIS Benchmarks** guidelines and File Integrity Monitoring (FIM).

This project was a great hands-on experience in hardening Linux servers, automating packet-filtering firewalls, correlating event logs, and implementing incident response playbooks.

👉 The complete lab report is available in PDF format.

What are your go-to open-source SIEM/SOAR tools for securing corporate environments?

#Cybersecurity #SIEM #SOAR #Wazuh #ThreatHunting #BlueTeam #SOC #ZeroTrust #SecOps #CISBenchmarks #Linux #Infosec

***
