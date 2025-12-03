# Particle Life - Simulation de Vie Artificielle
Une simulation évolutive de vie artificielle basée sur des particules avec algorithme génétique, développée en Rust avec le moteur de jeu Bevy et accélération GPU.

<p align="center">
  <img src="https://github.com/Onsraa/particle-life/blob/main/assets/gifs/simulated-particles.gif?raw=true" alt="Description du GIF" />
  <br>
  <u>Simulations de 20 populations de particules différentes</u>
</p>

## Description
Ce projet implémente un système de vie artificielle où des particules de différents types interagissent selon des forces d'attraction et de répulsion définies par leur génome. Le système utilise un algorithme génétique pour faire évoluer les populations de particules au fil des époques, permettant l'émergence de comportements complexes et d'espèces intéressantes.

### Caractéristiques principales
- **Simulation multi-population parallèle** : Plusieurs simulations s'exécutent simultanément avec des génomes différents

- **Algorithme génétique** : Évolution des génomes par sélection, crossover et mutation

- **Système de nourriture** : Les particules doivent collecter de la nourriture pour survivre

- **Matrice de forces personnalisable** : Chaque type de particule peut attirer ou repousser les autres types

- **Interface utilisateur interactive** : Contrôle en temps réel de la simulation et visualisation des matrices de forces

- **Sauvegarde/chargement de populations** : Préservez et étudiez les espèces intéressantes

- **Mode visualiseur** : Analysez en détail les espèces sauvegardées

## Architecture technique

### Technologies utilisées
- **Rust** (édition 2024) : Langage principal pour performance et sécurité
- **Bevy 0.16.1** : Moteur de jeu ECS (Entity Component System)
- **bevy_app_compute** : Intégration de compute shaders pour accélération GPU
- **bevy_egui** : Interface utilisateur immediate mode
- **bevy_spatial** : Structures spatiales pour détection de collisions optimisée

## Fonctionnement

### Système génétique
Chaque simulation possède un **génome** (Genotype) qui définit :
- **Matrice de forces** : Forces d'interaction entre chaque paire de types de particules
- **Forces de nourriture** : Attraction/répulsion de chaque type vers la nourriture

### Cycle évolutif
1. **Spawning** : Création des particules avec leurs génomes
2. **Simulation** : Les particules interagissent selon leurs forces génétiques
3. **Scoring** : Évaluation basée sur la survie et la collecte de nourriture
4. **Sélection** : Les meilleures simulations survivent (élitisme)
5. **Reproduction** : Crossover et mutation des génomes gagnants
6. **Nouvelle époque** : Recommence avec la nouvelle génération

### Paramètres de simulation
- **Nombre de simulations** : Populations parallèles (défaut: 9)
- **Particules par simulation** : Taille de chaque population (défaut: 500)
- **Types de particules** : Diversité génétique (défaut: 4 types)
- **Durée d'époque** : Temps avant sélection (défaut: 40s)
- **Taux de mutation** : Probabilité de mutation génétique
- **Ratio d'élite** : Proportion des meilleurs génomes préservés
- **Taux de crossover** : Fréquence de recombinaison génétique

## Remerciements
Inspiré par les travaux sur les systèmes de vie artificielle et les simulations de particules.

- Bevy : https://bevy.org/
- Evolving creatures using 3D particle life, Programming Chaos : https://www.youtube.com/watch?v=SVs4uDuyZPo