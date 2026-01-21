# 💇‍♀️ Bad Hair Day Predictor

<div align="center">

![Python](https://img.shields.io/badge/Python-3.9+-blue?logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-2.0+-green?logo=pandas&logoColor=white)
![Seaborn](https://img.shields.io/badge/Seaborn-Viz-orange?logo=python&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-yellow)

**Pipeline ETL intelligent pour prédire les pires moments capillaires de votre journée**

[📊 Résultats](#-aperçu-des-résultats) • [⚙️ Installation](#-installation-rapide) • [🧮 Méthodologie](#-méthodologie--le-bad-hair-index)

</div>

---

## 🎯 Objectif du Projet

> **Question centrale :** *Quand faut-il éviter de sortir pour préserver sa coiffure ?*

Ce projet construit un système d'analyse météorologique prédictive basé sur le **Bad Hair Index** — un indicateur combinant :
- 💧 **Humidité relative** (provoque les frisottis)
- 💨 **Vitesse du vent** (amplifie le désordre capillaire)

### 🎓 Contexte Académique
- **Rôle :** Analytics Engineer / Data Scientist
- **Formation :** Projet Python - Master 2 Économie Appliquée
- **Compétences :** Pipeline ETL • Feature Engineering • Data Visualization

---

## 📊 Aperçu des Résultats

### 1️⃣ Analyse Heure par Heure : Identifier les Créneaux à Risque

<p align="center">
  <img src="outputs/hour.png" alt="Analyse horaire du Bad Hair Index" width="750"/>
</p>

#### 🔍 Insights Clés par Tranche Horaire

| 🕐 Période | Index Moyen | Niveau | 💡 Recommandation |
|:-----------|:-----------:|:------:|:------------------|
| **08h - 09h** | 730+ | 🔴 **Critique** | Port du bonnet obligatoire |
| **13h - 14h** | ~610 | 🟢 **Optimal** | Fenêtre idéale pour les sorties |
| **18h - 20h** | 680+ | 🟠 **Modéré** | Spray anti-frisottis recommandé |

**📈 Analyse Détaillée :**
🔴 Pic Matinal (8h-9h)
└─ Combinaison humidité résiduelle + vent montant
└─ Action : Coiffure protectrice ou bonnet

🟢 Zone de Confort (13h)
└─ Assèchement naturel de l'air par le soleil
└─ Action : Moment optimal pour les rendez-vous

🟠 Remontée Progressive (18h+)
└─ Hausse de l'humidité au coucher du soleil
└─ Action : Prévoir protection légère

text

---

### 2️⃣ Analyse Jour par Jour : Planifier Stratégiquement la Semaine

<p align="center">
  <img src="outputs/day.png" alt="Analyse hebdomadaire du Bad Hair Index" width="750"/>
</p>

#### 📅 Tendances Hebdomadaires Observées
- **Jours à haut risque** : Lundi & Jeudi (perturbations fréquentes)
- **Jours favorables** : Mercredi & Samedi (conditions stables)
- **Variabilité saisonnière** : Écarts accentués en automne/printemps

---

## ⚙️ Stack Technique

### Architecture du Pipeline ETL

```mermaid
graph LR
    A[🌍 API Nominatim] -->|Géocodage| B[Extract]
    C[🌦️ API Open-Meteo] -->|Données Météo| B
    B --> D[Transform<br/>Pandas + NumPy]
    D --> E[Calculate Index]
    E --> F[📊 Visualisation<br/>Seaborn]
    F --> G[💾 Export PNG]
Composant	Technologie	Rôle
Extraction	requests	Appels API REST (Nominatim + Open-Meteo)
Transformation	pandas	Nettoyage JSON, parsing temporel
Calcul	numpy	Opérations vectorisées sur l'index
Visualisation	seaborn + matplotlib	Création de graphiques statistiques
Automatisation	os + pathlib	Gestion dynamique des répertoires
📁 Structure du Projet
text
03-projets_finaux/Prediction_meteo/
│
├── 📂 outputs/              # 🎨 Graphiques générés automatiquement
│   ├── day.png             # Analyse hebdomadaire (7 jours)
│   └── hour.png            # Analyse horaire (24h)
│
├── 📄 main.ipynb           # 🧪 Notebook Jupyter (pipeline complet)
├── 📄 README.md            # 📖 Documentation (ce fichier)
└── 📄 .gitignore           # 🚫 Fichiers exclus de Git
🧮 Méthodologie : Le "Bad Hair Index"
Formule de Calcul
L'indice capture l'effet synergique de deux facteurs météorologiques :

Bad Hair Index
=
Humidit
e
ˊ
 Relative (%)
×
Vitesse du Vent (km/h)
Bad Hair Index=Humidit 
e
ˊ
  Relative (%)×Vitesse du Vent (km/h)
📊 Échelle d'Interprétation
Index	Catégorie	Risque	Action Recommandée
< 500	🟢 Excellent	Minimal	Aucune précaution
500-700	🟡 Modéré	Moyen	Spray protecteur léger
700-900	🟠 Élevé	Important	Coiffure protectrice
> 900	🔴 Critique	Maximal	Éviter toute sortie
🔬 Justification Scientifique
Humidité Relative (%)

Provoque le gonflement de la cuticule capillaire

Responsable des frisottis et de la perte de volume

Vitesse du Vent (km/h)

Amplifie le désordre mécanique

Cause l'emmêlement et la déshydratation

Interaction Multiplicative

L'effet est synergique (non additif)

Un vent faible + forte humidité = Risque modéré

Un vent fort + forte humidité = Risque critique

Note : Basé sur des principes de cosmétologie capillaire (Journal of Cosmetic Science)

🚀 Installation Rapide
Prérequis
Python 3.9 ou supérieur

pip installé

Connexion Internet (appels API)

Étapes
bash
# 1. Cloner le projet
git clone https://github.com/votre-username/bad-hair-predictor.git
cd bad-hair-predictor

# 2. Installer les dépendances
pip install pandas seaborn matplotlib requests

# 3. Lancer le notebook
jupyter notebook main.ipynb
💻 Utilisation
Mode Notebook (Recommandé)
Ouvrez main.ipynb dans Jupyter

Exécutez les cellules séquentiellement

Les graphiques seront sauvegardés dans outputs/

Mode Script Python
python
from main import main

# Analyse pour une ville spécifique
main(
    country="France", 
    city="Montrouge", 
    agg_var="hour"  # ou "day"
)
Paramètres Personnalisables
Paramètre	Type	Description	Défaut
country	str	Pays de la ville	"France"
city	str	Nom de la ville	"Paris"
agg_var	str	Granularité ("hour" ou "day")	"hour"
days	int	Nombre de jours de prévision	7
📈 Exemple de Sortie
bash
🌍 Géocodage : Montrouge, France
📍 Coordonnées : 48.8167°N, 2.3167°E

🌦️  Récupération des données météo...
✅ 168 observations collectées (7 jours × 24 heures)

📊 Calcul du Bad Hair Index...
   - Index moyen : 645.3
   - Index max : 892.1 (Lundi 8h)
   - Index min : 423.7 (Mercredi 13h)

💾 Graphiques sauvegardés :
   ✓ outputs/hour.png
   ✓ outputs/day.png
🔮 Roadmap & Améliorations
Version 2.0 (Prévue Q2 2026)
 API REST : Déploiement Flask/FastAPI

 Dashboard Streamlit : Interface interactive

 ML Forecasting : Modèle LSTM pour prédictions 14 jours

 Notifications : Alertes SMS/Email pour indices > 850

 Multi-facteurs : Intégration température + pression

Features Expérimentales
 Indice spécifique par type de cheveux (bouclés, raides, afro)

 Historique de précision des prédictions

 Mode "Safe to Go Out" avec recommandations personnalisées

🤝 Contribution
Les contributions sont les bienvenues ! Pour contribuer :

Forkez le projet

Créez une branche (git checkout -b feature/AmazingFeature)

Committez (git commit -m 'Add: nouvelle feature')

Pushez (git push origin feature/AmazingFeature)

Ouvrez une Pull Request

📧 Contact
Moussa SISSOKO
🎓 Master 2 Économie Appliquée - Université de Lorraine
📧 Email : moussa.sissoko6@etu.univ-lorraine.fr
💼 LinkedIn : linkedin.com/in/moussa-sissoko
🐙 GitHub : @MoussaTheAnalyst

⚖️ Licence
Ce projet est sous licence MIT. Consultez le fichier LICENSE pour plus de détails.

🙏 Remerciements
Open-Meteo API pour les données météorologiques gratuites

Nominatim (OpenStreetMap) pour le géocodage

Seaborn/Matplotlib pour les visualisations

Université de Lorraine pour l'encadrement académique

<div align="center">
⭐ Si ce projet vous a été utile, n'hésitez pas à lui donner une étoile !

Made with ❤️ and ☕ by Moussa SISSOKO

</div> ```
