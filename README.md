# 🖥️ Homelab — Infrastructure d'entreprise virtualisée


Projet personnel de homelab visant à reproduire l'infrastructure réseau et
système d'une PME (annuaire, DNS/DHCP, pare-feu, supervision, sécurité)
entièrement virtualisée sur mon PC.


---

## 🎯 Objectifs du projet

- Construire un réseau d'entreprise segmenté et réaliste (LAN interne / DMZ / segment sécurité)
- Mettre en pratique l'administration système et réseau (AD, DNS, DHCP, pare-feu, GPO)
- M'entraîner à la supervision et à la détection d'intrusion
- Documenter proprement le projet comme un vrai portfolio technique

## 🏗️ Architecture

'''
                         INTERNET (NAT)
                              │
                        ┌─────▼─────┐
                        │  pfSense  │  Firewall / Routeur / VPN
                        └─────┬─────┘
              ┌───────────────┼───────────────────┐
              │                │                    │
   LAN INTERNE 10.0/24   DMZ 20.0/24         SEGMENT SÉCU 30.0/24
   ─────────────────     ─────────────       ─────────────────────
   • AD DS / DNS / DHCP  • Serveur Web        • Zabbix / Centreon
   • WSUS / Fichiers     • DNS secondaire     • Wazuh (SIEM)
   • Client Windows 11                        • Kali (isolée)
   • Client Debian
'''


## 🧰 Stack technique

| Catégorie | Outils |
|---|---|
| Hyperviseur | VMware Workstation Pro |
| Pare-feu / Routage | pfSense |
| Annuaire | Windows Server 2022 — AD DS, DNS, DHCP, GPO |
| Services | WSUS, serveur de fichiers |
| Web | Debian + Nginx |
| Supervision | Zabbix / Centreon |
| Sécurité | Wazuh (SIEM), Kali Linux |
| Documentation | Markdown, GitHub |

## 🗺️ Roadmap

- [ ] **Phase 1** — Socle réseau (pfSense, segmentation, règles de filtrage)
- [ ] **Phase 2** — Annuaire (AD DS, DNS, DHCP, GPO)
- [ ] **Phase 3** — Services métier (WSUS, fichiers, web en DMZ)
- [ ] **Phase 4** — Supervision & sécurité (Zabbix, Wazuh, tests pentest)
- [ ] **Phase 5** — Documentation finale (procédures, matrice de flux)

Suivi détaillé et journal d'avancement : [`docs/PROGRESS.md`](docs/PROGRESS.md)

## 📂 Structure du repo

'''
homelab-sisr/
├── README.md
├── docs/
│   ├── architecture.md       # Schéma réseau, plan d'adressage, matrice de flux
│   ├── schema-reseau.drawio  # Schéma réseau modifiable (draw.io)
│   ├── PROGRESS.md           # Journal d'avancement (source pour LinkedIn)
│   ├── LINKEDIN_TEMPLATES.md # Templates de posts
│   ├── phase-1-pfsense.md
│   ├── phase-2-active-directory.md
│   ├── phase-3-services.md
│   ├── phase-4-supervision-securite.md
│   └── phase-5-documentation.md
└── screenshots/               # Captures d'écran des configs / dashboards
'''

## 📖 Journal de bord

Chaque étape est documentée dans `docs/` avec : objectif, étapes suivies,
difficultés rencontrées et captures d'écran.

## 📝 Licence

Projet personnel — libre de réutilisation à but d'apprentissage.
