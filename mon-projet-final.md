# Mise en œuvre des KPI pour les Projets IT d’Ikatel Mali

## Introduction

La gestion efficace des projets IT repose sur la capacité à mesurer et piloter la performance. Les indicateurs clés de performance (KPI) sont des outils essentiels pour assurer le suivi, l’optimisation et la réussite des initiatives informatiques. Ce document présente une démarche structurée pour la mise en place des KPI au sein des projets IT d’Ikatel Mali, en détaillant les outils, méthodes et bonnes pratiques à adopter.

---

## Pourquoi mettre en place des KPI ?

Les indicateurs clés de performance (KPI) sont essentiels pour :

- Mesurer concrètement les progrès réalisés
- Vérifier si les investissements produisent les bénéfices attendus
- Prendre des décisions rapidement et efficacement
- Assurer la conformité et la qualité de chaque initiative

---

## Comment structurer le suivi des KPI ?

### Pilotage clair et structuré

Pour chaque projet IT, une gouvernance adaptée est mise en place :

- **Comité de pilotage global** : directions IT, Finance, Sécurité, Marketing, etc.
- **Responsable par projet** : assure le suivi des KPI
- **Revues régulières** :
  - Mensuelles : suivi opérationnel
  - Trimestrielles : ajustements stratégiques

---

## Outils utilisés

| Domaine       | Outils recommandés                     | Détails techniques                                                                                                                           |
| ------------- | -------------------------------------- | -------------------------------------------------------------------------------------------------------------------------------------------- |
| ERP           | Odoo, SAP                              | Extraction via API REST / Webhooks pour collecter les journaux d’activité, les événements métier, et les erreurs système                     |
| Mobile        | Firebase, Google Analytics             | SDK intégré dans l'app pour tracker les événements utilisateurs (login, clic, conversion). Export vers BigQuery pour analyses personnalisées |
| Cybersécurité | QRadar, Splunk, outils de surveillance | Agrégation de logs réseau, détection de comportements anormaux via règles corrélées et machine learning                                      |

---

## KPI par projet

### Projet 1 : Nouvel ERP

**Objectif** : Automatiser les processus internes et réduire les coûts.

**Indicateurs** :

- Pourcentage de processus automatisés
- Coût moyen par transaction
- Temps de traitement d’un document
- Nombre d’erreurs détectées (audit)
- Disponibilité du système (uptime)

**Collecte & Traitement** :

- Utilisation des webhooks Odoo pour notifier en temps réel les modifications de statut (ex. : commande validée)
- Analyse des logs de traitement pour mesurer le temps moyen par processus
- Intégration avec un outil de BI (ex. : Power BI, Metabase) pour visualiser les KPI

---

### Projet 2 : Application Mobile

**Objectif** : Attirer de nouveaux clients et augmenter le chiffre d’affaires.

**Indicateurs** :

- Utilisateurs actifs mensuels (MAU)
- Taux de conversion visiteurs → abonnés
- Revenu moyen par utilisateur (ARPU)
- Taux de rétention à 30 jours
- Satisfaction utilisateur
- Conformité RGPD / APDP

**Collecte & Monitoring** :

- Firebase Analytics pour tracker les événements (screen_view, purchase, session_start)
- Connexion BigQuery ↔ Looker Studio pour analyser les parcours utilisateur
- Système d’alerte via Slack ou email si le MAU ou le taux de conversion chute sous un seuil critique

---

### Projet 3 : Cybersécurité

**Objectif** : Prévenir les incidents et renforcer la confiance.

**Indicateurs** :

- Temps moyen de détection (MTTD)
- Temps moyen de résolution (MTTR)
- Incidents évités
- Pourcentage de failles corrigées rapidement
- Résultats des audits ISO / NIST
- Taux de faux positifs

**Détection & Réaction** :

- QRadar agrège les logs de pare-feu, Active Directory, antivirus
- Scripts Python déclenchés automatiquement pour corriger certaines vulnérabilités (via Ansible ou SOAR)
- Tableaux de bord dynamiques (Grafana, Kibana) pour afficher le MTTR et MTTD en temps réel

---

## Suivi global et pilotage

Un tableau de bord centralisé permet de :

- Suivre l’évolution de chaque projet
- Identifier les zones à améliorer
- Renforcer la collaboration inter-équipes

**Infrastructure recommandée** :

- Base de données centrale de type PostgreSQL pour stocker les KPI de chaque projet
- Pipeline ETL automatisé (Apache NiFi, Talend, ou scripts Python avec CRON) pour collecter les données brutes, les transformer et les stocker
- Tableau de bord unifié (Power BI, Grafana, Looker Studio) avec actualisation automatique (ex. : toutes les heures)

Chaque KPI inclut :

- Une valeur cible (ex. : 80 % d’automatisation)
- Une fréquence de suivi (hebdomadaire, mensuelle, etc.)
- Un responsable clairement identifié

---

## Points de vigilance

### Risques

- Données de mauvaise qualité
- KPI mal définis
- Manque d’adhésion des utilisateurs
- Difficultés d’interprétation

### Recommandations

- Former les équipes aux KPI
- Mettre en place des alertes
- Revoir régulièrement les indicateurs
- Associer des indicateurs qualitatifs (satisfaction)

### Défis techniques et solutions

- **Qualité des données** : Utilisation de librairies comme Great Expectations pour valider les jeux de données avant intégration
- **Sécurité des données KPI** : Chiffrement des flux avec TLS, gestion des droits d’accès par rôle (RBAC)
- **Scalabilité** : Architecture modulaire avec possibilité de traitement en batch ou en streaming selon le volume (Kafka + Spark)

---

## Conclusion

La mise en œuvre des KPI constitue un levier stratégique pour garantir :

- L’optimisation des ressources
- La création de valeur
- Une culture de pilotage par la donnée, reposant sur une architecture technique robuste

---

*TOURE Mamadou*
