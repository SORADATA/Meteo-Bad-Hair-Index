# 💇‍♀️ Bad Hair Day Predictor

<div align="center">

![Python](https://img.shields.io/badge/Python-3.9+-blue?logo=python&logoColor=white)
![Pandas](https://img.shields.io/badge/Pandas-2.0+-green?logo=pandas&logoColor=white)
![Seaborn](https://img.shields.io/badge/Seaborn-Viz-orange?logo=python&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-yellow)

**Pipeline ETL pour prédire les moments capillaires à risque basé sur les données météorologiques**

[📊 Résultats](#résultats) • [⚙️ Installation](#installation) • [🧮 Méthodologie](#méthodologie)

</div>

---

## 🎯 Objectif

Analyse prédictive des conditions météorologiques défavorables pour la coiffure via le **Bad Hair Index**, combinant humidité et vitesse du vent pour identifier les créneaux horaires à éviter.

 
**Compétences :** Pipeline ETL • Feature Engineering • Data Visualization

---

## 📊 Résultats

### Analyse Horaire

<p align="center">
  <img src="outputs/hour.png" alt="Analyse horaire du Bad Hair Index" width="700"/>
</p>

| Période | Index Moyen | Recommandation |
|:--------|:-----------:|:---------------|
| **08h - 09h** | 730+ | 🔴 Risque élevé |
| **13h - 14h** | ~610 | 🟢 Fenêtre optimale |
| **18h - 20h** | 680+ | 🟠 Risque modéré |

### Analyse Hebdomadaire

<p align="center">
  <img src="outputs/day.png" alt="Analyse hebdomadaire" width="700"/>
</p>

---

## 🧮 Méthodologie

### Formule du Bad Hair Index

```
Bad Hair Index = Humidité Relative (%) × Vitesse du Vent (km/h)
```

### Échelle d'Interprétation

| Index | Niveau | Action |
|:-----:|:-------|:-------|
| < 500 | 🟢 Faible | Aucune précaution |
| 500-700 | 🟡 Modéré | Protection légère |
| 700-900 | 🟠 Élevé | Coiffure protectrice |
| > 900 | 🔴 Critique | Éviter les sorties |

**Justification :** L'humidité provoque les frisottis, le vent amplifie le désordre. Leur interaction multiplicative capture l'effet synergique sur la structure capillaire.

---

## ⚙️ Stack Technique

- **Extraction :** `requests` (API Nominatim + Open-Meteo)
- **Transformation :** `pandas`, `numpy`
- **Visualisation :** `seaborn`, `matplotlib`

---

## 🚀 Installation

### Prérequis
- Python 3.9+
- Connexion Internet

### Setup

```bash
# Cloner le repository
git clone https://github.com/MoussaTheAnalyst/bad-hair-predictor.git
cd bad-hair-predictor

# Installer les dépendances
pip install pandas seaborn matplotlib requests numpy

# Lancer le notebook
jupyter notebook main.ipynb
```

---

## 💻 Utilisation

```python
from main import main

# Analyse pour une ville
main(
    country="France", 
    city="Montrouge", 
    agg_var="hour"  # ou "day"
)
```

### Paramètres

| Paramètre | Type | Description | Défaut |
|:----------|:-----|:------------|:-------|
| `country` | str | Pays | "France" |
| `city` | str | Ville | "Paris" |
| `agg_var` | str | Granularité ("hour"/"day") | "hour" |
| `days` | int | Jours de prévision | 7 |

---

## 📁 Structure

```
bad-hair-predictor/
├── outputs/          # Graphiques générés
│   ├── day.png
│   └── hour.png
├── main.ipynb        # Pipeline complet
└── README.md
```

---

## 🔮 Évolutions Futures

- API rest
- API meteo
  


---

## 📧 Contact

**Moussa Thiam** - Data Analyst  
📧 [Email](mailto:your.email@example.com) • 💼 [LinkedIn](https://linkedin.com/in/yourprofile) • 🐙 [GitHub](https://github.com/MoussaTheAnalyst)

---

<div align="center">

**⭐ Si ce projet vous aide, n'hésitez pas à lui donner une étoile !**

</div>
