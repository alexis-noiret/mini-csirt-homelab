# 🛡️ Mini-CSIRT Homelab

Un mini centre de réponse à incident (CSIRT) monté dans mon homelab : je rejoue des attaques sur un Active Directory durci, je les détecte avec un SIEM, puis je les traite comme le ferait un analyste CSIRT : qualification, rapport d'incident, gestion des vulnérabilités, automatisation et tableau de bord.

> 🚧 Projet en cours : le dépôt se remplit au fil des étapes (voir la feuille de route).

---

## 🎯 Objectifs

- Traiter des alertes de sécurité de bout en bout : détection, qualification, confinement, remédiation, retour d'expérience
- Documenter chaque incident dans un rapport structuré, rattaché à une technique MITRE ATT&CK
- Mettre en place une gestion des vulnérabilités priorisée (CVSS, EPSS, catalogue CISA KEV), y compris pour la surface exposée sur Internet
- Automatiser l'enrichissement et le triage des alertes (Python, PowerShell)
- Produire des KPI de cybersécurité dans un tableau de bord Power BI

## 🏗️ Architecture du laboratoire

| Brique | Rôle |
|---|---|
| pfSense | Pare-feu / routeur, VPN WireGuard d'accès distant |
| Proxmox VE | Hyperviseur hébergeant les machines virtuelles |
| Windows Server (Active Directory) | Cible durcie |
| Windows Client | Poste du domaine |
| Kali Linux | Machine d'attaque (labo isolé, usage légal uniquement) |
| Wazuh | SIEM : collecte, détection, alertes |
| Ubuntu | Poste d'administration et de scripts |

Un schéma détaillé sera ajouté dans `docs/architecture.md`.

## 🗂️ Structure du dépôt

```
mini-csirt-homelab/
├── docs/                 # Architecture, notes de conception
├── templates/            # Modèle de rapport d'incident
├── incidents/            # Un dossier par incident (INC-AAAA-NNN)
├── vuln-mgmt/            # Scans et priorisation des vulnérabilités
├── automation/
│   ├── python/           # Enrichissement et triage des alertes
│   └── powershell/       # Remédiation côté Active Directory
└── dashboards/           # Tableaux de bord Power BI
```

## 🧭 Feuille de route

| # | Étape | Statut |
|---|---|---|
| 0 | Dépôt Git et trame de rapport d'incident | 🔄 En cours |
| 1 | INC-2026-001 : NetExec contre l'AD durci, détecté dans Wazuh | ⏳ À faire |
| 2 | Incidents n°2 et 3 (autres techniques ATT&CK) | ⏳ À faire |
| 3 | Script Python : API Wazuh vers CSV enrichi | ⏳ À faire |
| 4 | Gestion des vulnérabilités (Greenbone, CVSS / EPSS / KEV) | ⏳ À faire |
| 5 | Tableau de bord Power BI | ⏳ À faire |
| 6 | PowerShell et réponse active Wazuh | ⏳ À faire |
| 7 | Finalisation : schéma, README, retour d'expérience | ⏳ À faire |

## 🧠 Compétences démontrées

Cette section sera complétée à mesure que les étapes sont réalisées.

- 🔍 Analyse et qualification d'alertes (SIEM Wazuh)
- 🚨 Gestion d'incident et rédaction de rapports
- 🗺️ Cartographie MITRE ATT&CK
- 🩹 Gestion et priorisation des vulnérabilités
- 🤖 Scripts d'automatisation (Python, PowerShell)
- 📊 Reporting et KPI (Power BI)
- 🌿 Versionnement Git / GitHub

## ⚠️ Avertissement

Toutes les attaques sont réalisées dans mon laboratoire personnel, isolé, sur mes propres machines. Aucun outil offensif n'est utilisé en dehors de ce cadre.

## 👤 Auteur

**Alexis Noiret**, étudiant en Bachelor IT Cybersécurité à La Plateforme

- 🌐 Portfolio : [alexis-noiret.students-laplateforme.io](https://alexis-noiret.students-laplateforme.io)
- 💻 GitHub : [github.com/alexis-noiret](https://github.com/alexis-noiret)
