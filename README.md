# Rapport d'Interception de Trafic - Lab Pentest Mobile

> **Description :** Fiche de trace documentant l'interception et l'analyse du trafic réseau d'un émulateur Android via un proxy Man-In-The-Middle (MITM). Ce travail a été réalisé dans le cadre d'un laboratoire d'audit de sécurité mobile.

---

##  1. Périmètre
* **Environnement :** Émulateur de laboratoire Android (Appareil cible autorisé).
* **Objectif :** Validation de l'interception du trafic réseau via un proxy MITM.

##  2. Configuration
* **Outil d'interception :** Burp Suite Community Edition v2026.2.3
* **Configuration Proxy :** Trafic intercepté via l'hôte (`192.168.100.14/8081`).
* **Date de l'audit :** 5 Mars 2026 à 19:31:35

---

## 3. Preuves

### Historique des requêtes
Capture des requêtes sortantes automatisées du système Android vers les domaines de vérification de connectivité (`www.google.com`, `connectivitycheck.gstatic.com`, etc.).

![Historique des requêtes HTTP dans Burp Suite]
<img width="1920" height="906" alt="{57B22A26-1CEB-4A1E-9F2A-2EE64F37AF42}" src="https://github.com/user-attachments/assets/3265df09-d7fa-44bd-bf9c-5751423185e2" />
<img width="1386" height="902" alt="{A8223918-8056-4E21-9B23-6033E02055EC}" src="https://github.com/user-attachments/assets/2306a35f-8b6d-424e-9ea9-d4b9b1c0218d" />

<img width="388" height="498" alt="{EB6C7A7B-C435-421F-A441-F0AA467D5D91}" src="https://github.com/user-attachments/assets/7aeff18b-6630-475e-ad3d-2a4ef431bca2" />



### Détails de la requête interceptée
* **Protocole/Méthode :** HTTP/1.1 `GET`
* **URL cible :** `http://www.google.com/gen_204`

**En-têtes HTTP (Headers) :**
```http
GET /gen_204 HTTP/1.1
Host: [www.google.com](https://www.google.com)
User-Agent: Mozilla/5.0 (X11; Linux x86_64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/60.0.3112.32 Safari/537.36
Connection: keep-alive
Accept-Encoding: gzip, deflate, br
