Infrastructure réseau sécurisée sous Proxmox

Présentation du projet
Ce projet consiste à concevoir et documenter une infrastructure réseau virtualisée
orientée systèmes, réseaux et cybersécurité, déployée sous Proxmox VE.

L’objectif est de mettre en place une architecture segmentée, sécurisée et évolutive,
en intégrant des notions de supervision, détection d’intrusion et résilience.

Objectifs
- Concevoir une infrastructure réseau cohérente
- Segmenter les rôles et les services
- Mettre en œuvre des principes de sécurité (accès, journalisation, détection)
- Documenter une architecture de manière professionnelle

Environnement technique
- Hyperviseur : Proxmox VE
- Systèmes : Linux (Ubuntu Server / Debian)
- Réseau : bridges virtuels, segmentation logique
- Services : SSH, DNS, Apache, SIEM, NIDS
- Sécurité : WAF, centralisation des logs, supervision

Architecture de l’infrastructure
L’infrastructure est organisée en plusieurs zones logiques, chacune ayant un rôle
précis afin de limiter la surface d’attaque et améliorer la visibilité sécurité.

Schéma disponible dans : `docs/schema-infrastructure-proxmox.png`

Accès administrateur
- Bastion SSH dédié
- Accès centralisé et contrôlé aux serveurs internes

SOC (Security Operations Center)
- Serveur de gestion des correctifs
- Centralisation et analyse des logs
- SIEM pour la corrélation des événements
- NIDS pour la détection d’intrusions réseau

Zone Web
- Serveur DNS interne
- WAF pour la protection applicative
- Load Balancer
- Serveur Web Apache
- Machine client de test

Zone Base de Données
- Serveur BDD maître
- Serveur BDD esclave (réplication)

Zone de sauvegarde et d’archivage
- Environnement isolé
- Serveur de sauvegarde primaire
- Serveur de sauvegarde secondaire
- Données hors production
- Réduction du risque de propagation (ransomware)
- Isolation logique du reste de l’infrastructure

Approche sécurité
- Segmentation des rôles
- Principe du moindre privilège
- Centralisation des journaux
- Détection et analyse des incidents
- Sauvegardes isolées

Structure du projet
infra-reseau-proxmox/
├── README.md
├── docs/
│ └── schema-infrastructure-proxmox.png
├── config/
│ └── exemples-config.txt
└── screenshots/

Évolutions possibles
- Mise en place de VLAN
- Pare-feu avancé
- IDS/IPS
- Supervision graphique
- VPN d’accès sécurisé

Contexte
Projet réalisé dans un cadre pédagogique afin de développer des compétences
en administration systèmes, réseaux et cybersécurité.
