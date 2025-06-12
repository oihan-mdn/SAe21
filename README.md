# SAÉ21 – Construction d’un réseau informatique multisite pour CDS25

Bienvenue dans le dépôt GitHub de notre projet **SAÉ21**, réalisé dans le cadre du BUT1 Réseaux & Télécommunications à l'IUT de Blagnac.

Projet composé de: Oihan Martin Dit Neuville, Hugo Diniz, Sarah Perez et Timéo Champigny

**Sujet** : Mise en place d’un réseau informatique pour une entreprise multisite fictive : **CDS25**

## Cahier des charges

L’entreprise est répartie sur 4 sites en France :

| **Site**        | **Stagiaires** | **Salariés** | **Téléphones IP** |
| ------------------ | -------------------: | -----------------: | -------------------: |
| Paris           |                   70 |                 20 |                    8 |
| Rennes          |                   24 |                 12 |                    4 |
| Pointe-à-Pitre  |                   15 |                  7 |                    2 |
| Limoges (siège) |                   96 |                 30 |                   12 |

### Objectifs techniques

- Réseaux VLANs : stagiaires, salariés, VoIP, serveurs  
- DHCP centralisé  
- Routage inter-VLAN + inter-sites (statique)  
- Services : HTTP, DNS, SSH  
- Accès Wi-Fi pour stagiaires/invités  
- Téléphonie IP (SIP)  
- Infrastructure testée sur Cisco Packet Tracer **et en TP**

## Compétences mobilisées

| **Ressource** | **Compétence mobilisée**                                   |
| ---------------- | -------------------------------------------------------------- |
| `R101` à `R103`  | Conception réseau local, adressage IP, VLANs                   |
| `R201` à `R203`  | Routage statique, DHCP, DNS, SSH, services réseau              |
| `R202`           | Configuration serveur Linux (DHCP, DNS, HTTP)                  |
| `R210` / `R211`  | Communication technique & documentation structurée             |
| `R115`           | Gestion de projet (diagramme de Gantt, répartition des tâches) |

## Architecture réseau

- 4 routeurs principaux (1 par site)  
- Liaisons inter-sites via réseau WAN (`10.0.X.0/30`)  
- Plan IP structuré en sous-réseaux :
  - VLAN 10 : Stagiaires  
  - VLAN 20 : Salariés  
  - VLAN 30 : VoIP  
  - VLAN 99 : Serveurs (DHCP/DNS/HTTP)  
- Serveur centralisé à Limoges

## Tests & preuves de concept

| **Test réalisé**                           | **Résultat attendu**          | **Statut** |
| --------------------------------------------- | -------------------------------- | ------------ |
| Attribution DHCP par VLAN                     | IP dynamique dans chaque VLAN    | 🟡 En cours  |
| Routage inter-sites (Ping Paris ↔ Limoges...) | Latence < 50ms                   | 🟡 En cours  |
| Accès HTTP serveur web Limoges                | Page affichée dans navigateur    | 🟡 En cours  |
| Résolution DNS (serveur local)                | Résolution `nom → IP`            | 🟡 En cours  |
| Connexion SSH depuis PC salarié vers serveur  | Authentification & shell distant | 🟡 En cours  |
| Téléphones IP avec DHCP + SIP                 | IP attribuée, communication SIP  | 🟡 En cours  |
| Wi-Fi stagiaires (AP VLAN 10)                 | Connecté, IP reçue via DHCP      | 🟡 En cours  |

## Contenu du dépôt

