# Analyse des Réseaux Sociaux — LastFM Asia Social Network

> Projet réalisé dans le cadre du cours **Analyse des Réseaux Sociaux 2026**

---

## Description

Ce projet porte sur l'analyse complète du réseau social **LastFM Asia**, un graphe d'utilisateurs de la plateforme de streaming musical Last.fm en Asie. Le travail est structuré en trois parties : collecte des données, analyse structurelle du réseau, et détection de communautés.

---

## Structure du dépôt

```
 projet-ARS2026/
├──  ARS2026_LastFM_Analysis.ipynb     # Code complet (Partie 1, 2 & 3)
├──  ARS2026_LastFM_Rapport.ipynb      # Rapport final (format Jupyter)
├──  data/
│   ├── edges.csv                        # Arêtes du réseau (amitiés)
│   ├── targets.csv                      # Labels des nœuds (pays)
│   ├── fig1_degree.png                  # Distribution des degrés
│   ├── fig2_paths.png                   # Distribution des chemins
│   ├── fig3_clustering.png              # Coefficient de clustering
│   ├── fig4_centrality.png              # Mesures de centralité
│   ├── fig5_community_sizes.png         # Tailles des communautés
│   └── fig6_network_viz.png             # Visualisation du réseau
└── README.md
```

---

## Dataset — LastFM Asia Social Network

| Propriété | Valeur |
|-----------|--------|
| **Source** | [SNAP Stanford](https://snap.stanford.edu/) / [Rozemberczki & Sarkar, 2020](https://github.com/benedekrozemberczki/datasets) |
| **Nœuds** | Utilisateurs Last.fm (Asie) |
| **Liens** | Amitiés mutuelles (non orienté) |
| **Attributs** | Label de pays de localisation |
| **Nœuds** | ~7 600 |
| **Arêtes** | ~27 800 |

---

## Parties du projet

### Partie 1 — Collecte des données
- Identification de la source (API publique Last.fm via GitHub)
- Téléchargement automatique avec fallback garanti
- Construction du graphe NetworkX avec attributs de nœuds

### Partie 2 — Analyse du réseau
-  **Distribution des degrés** — loi de puissance (*scale-free*)
-  **Composants connectés** — composant géant dominant
-  **Analyse des chemins** — phénomène *small-world*
-  **Clustering et densité** — fort coefficient de clustering local
-  **Centralité** — degree, betweenness, closeness, eigenvector

### Partie 3 — Détection de communautés
Comparaison de 4 algorithmes via **CDlib** :

| Algorithme | Type | Complexité |
|------------|------|------------|
| **Louvain** | Non-chevauchant | O(n log n) |
| **Label Propagation** | Non-chevauchant | O(n + m) |
| **Infomap** | Non-chevauchant | O(n log n) |
| **K-Clique (k=3)** | Chevauchant | NP-difficile |

---

## Technologies utilisées

![Python](https://img.shields.io/badge/Python-3.10+-3776AB?style=flat&logo=python&logoColor=white)
![NetworkX](https://img.shields.io/badge/NetworkX-3.x-orange?style=flat)
![CDlib](https://img.shields.io/badge/CDlib-0.3.x-blueviolet?style=flat)
![Jupyter](https://img.shields.io/badge/Jupyter-Notebook-F37626?style=flat&logo=jupyter&logoColor=white)

```
networkx · matplotlib · seaborn · pandas · numpy · cdlib
```

---

## Lancer le projet

### 1. Cloner le dépôt
```bash
git clone https://github.com/VOTRE_COMPTE/projet-ARS2026.git
cd projet-ARS2026
```

### 2. Installer les dépendances
```bash
pip install networkx matplotlib seaborn pandas numpy cdlib requests
```

### 3. Ouvrir le notebook
```bash
jupyter notebook ARS2026_LastFM_Analysis.ipynb
```

 Le dataset est téléchargé automatiquement au lancement. En cas d'échec réseau, un graphe synthétique équivalent est généré automatiquement.

---

## Rapport

Le rapport complet (≤ 10 pages) est disponible dans le fichier :
**`ARS2026_LastFM_Rapport.ipynb`**

Il inclut l'interprétation de chaque résultat, les tableaux de métriques et les figures annotées.

---

## Références principales

- Rozemberczki & Sarkar, *Characteristic Functions on Graphs*, CIKM 2020
- Barabási & Albert, *Emergence of Scaling in Random Networks*, Science 1999
- Watts & Strogatz, *Collective dynamics of small-world networks*, Nature 1998
- Blondel et al., *Fast unfolding of communities in large networks*, J. Stat. Mech. 2008
- Rossetti et al., *CDlib: a Python Library*, Applied Network Science 2019

---

## Auteur

**[Diffo Othniel Armstrong]**  
