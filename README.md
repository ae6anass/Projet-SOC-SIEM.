# 🛡️ Projet SOC/SIEM : Déploiement et Défense Active (SOAR) avec Wazuh

**Auteur :** Anass Es-Saghir (Élève Ingénieur ISIC – ENSA El Jadida)  
**Domaine :** Cybersécurité (Blue Team), Administration Système, Sécurité Réseau  

---

## 📝 Description du Projet

Ce projet de laboratoire démontre la capacité à déployer, configurer et administrer un environnement de détection et de réponse aux incidents (SIEM/SOAR) de bout en bout en utilisant la solution **Wazuh**. L'objectif principal est de dépasser la simple supervision passive en implémentant des mécanismes de **Défense Active** et de détection post-exploitation.

Le laboratoire s'articule autour de deux scénarios d'ingénierie de sécurité (Blue Team) :
1. **Défense Périphérique et SOAR :** Détection en temps réel d'une attaque externe par force brute (SSH), couplée à une réponse automatisée (*Active Response*) bloquant dynamiquement l'adresse IP de l'attaquant.
2. **Surveillance Post-Exploitation (Zero Trust) :** Détection des menaces internes par l'analyse des journaux d'authentification (PAM) pour isoler les utilisateurs tentant de forcer l'accès root via un abus de privilèges Sudo.

---

## 🏗️ Architecture de l'Environnement de Test

L'infrastructure a été segmentée pour isoler les différents rôles :
* **Serveur SIEM (Wazuh Manager) :** Serveur centralisé chargé de la corrélation des événements et de l'orchestration des réponses.
* **Machine Cible (Wazuh Agent) :** Environnement Ubuntu surveillé, configuré pour transmettre les journaux d'audit système et exécuter les scripts de blocage.
* **Machine Attaquante :** Hôte ThinkPad (Linux Mint) utilisé pour simuler les vecteurs d'attaque.

---

## 🚀 Scénario 1 : Attaque Réseau et Réponse Automatisée (SOAR)

### 1. L'Attaque Initiale (Brute Force SSH)
Depuis la machine attaquante, une attaque par dictionnaire a été lancée à l'aide de l'outil `hydra` pour compromettre le service SSH de la cible.

<img width="718" height="394" alt="image" src="https://github.com/user-attachments/assets/5307b463-395b-4fac-a53e-732902af48cd" />


### 2. Implémentation de la Défense Active
Le serveur Wazuh a été configuré (`ossec.conf`) pour réagir automatiquement à la règle ID `5763` (SSH Brute Force). Le Manager ordonne à l'Agent d'exécuter le script `firewall-drop`, isolant l'IP offensive pendant 300 secondes.

### 3. Validation du Confinement
Dès le déclenchement de l'Active Response, toute nouvelle tentative de connexion de l'attaquant vers la cible est rejetée silencieusement par le pare-feu (`Connection timed out`).

<img width="373" height="42" alt="image" src="https://github.com/user-attachments/assets/8a98d043-f89e-4c23-a97a-dc54d04a1116" />


---

## 🔍 Scénario 2 : Détection des Menaces Internes (Abus de Privilèges)

Une fois le périmètre sécurisé, le laboratoire a basculé sur la détection des mouvements latéraux et de l'élévation de privilèges par un utilisateur interne non autorisé.

### 1. Simulation de la Compromission Interne
Un utilisateur standard (non privilégié) nommé `stagiaire` tente d'accéder aux secrets du système (`/etc/shadow`) en forçant la commande `sudo`. Le système d'exploitation rejette la demande et génère des logs d'audit critiques.

<img width="510" height="168" alt="image" src="https://github.com/user-attachments/assets/f437b68a-bf12-4899-869e-c60b0dcb418e" />


### 2. Corrélation et Remontée SIEM
Le module de *Threat Hunting* de Wazuh analyse les journaux PAM et déclenche instantanément des alertes de haute sévérité. L'incident est isolé et documenté prouvant l'efficacité de la surveillance interne.

<img width="746" height="530" alt="image" src="https://github.com/user-attachments/assets/8b752515-a897-4d55-aec9-7a9d7a032606" />


---

## 🗺️ Mapping MITRE ATT&CK

Ce laboratoire couvre et détecte de manière proactive les tactiques et techniques suivantes :
* **T1110.001 :** Brute Force: Password Guessing
* **T1021.004 :** Remote Services: SSH
* **T1548.003 :** Abuse Elevation Control Mechanism: Sudo and Sudo Caching
* **T1078.003 :** Valid Accounts: Local Accounts

---

## 🛠️ Compétences Démontrées
* **Administration Linux & Réseau :** SSH, pare-feu (iptables/ufw), gestion des utilisateurs et permissions (PAM, sudoers).
* **Ingénierie SIEM :** Configuration XML (`ossec.conf`), débogage d'agents de sécurité, création de règles de corrélation.
* **Automatisation (SOAR) :** Déploiement de scripts de réponse active conditionnels.
