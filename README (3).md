# Anime Face Generator with DCGAN

Ce projet est un notebook Jupyter qui utilise un **DCGAN (Deep Convolutional Generative Adversarial Network)** pour générer des visages d'anime à partir d'un ensemble de données d'images d'anime. Le modèle est composé de deux réseaux de neurones : un **generator** (générateur) et un **discriminator** (discriminateur). Le notebook est conçu pour être exécuté sur Kaggle, où il peut tirer parti de l'accélération GPU pour accélérer le processus de formation du modèle.

## Table des matières

1. [Introduction](#introduction)
2. [Architecture du DCGAN](#architecture-du-dcgan)
3. [Installation](#installation)
4. [Utilisation](#utilisation)
5. [Structure du projet](#structure-du-projet)
6. [Dépendances](#dépendances)
7. [Licence](#licence)

---

## Introduction

Ce projet vise à créer un modèle de génération d'images de visages d'anime en utilisant un **DCGAN** (Deep Convolutional Generative Adversarial Network). Le modèle est composé de deux parties principales :
- **Generator** : Génère de nouvelles images à partir d'un vecteur de bruit aléatoire.
- **Discriminator** : Distingue les images réelles des images générées par le générateur.

Le modèle est entraîné sur un ensemble de données contenant des milliers d'images de visages d'anime. Une fois entraîné, le générateur peut produire de nouvelles images de visages d'anime qui n'existaient pas auparavant.

---

## Architecture du DCGAN

### Generator
Le générateur prend un vecteur de bruit aléatoire en entrée et le transforme en une image de visage d'anime. Il utilise des couches de **transposed convolution** pour augmenter progressivement la résolution de l'image jusqu'à obtenir une image de la taille souhaitée (par exemple, 64x64 pixels).

### Discriminator
Le discriminateur est un classificateur qui prend une image en entrée et détermine si elle est réelle (provenant de l'ensemble de données) ou générée (produite par le générateur). Il utilise des couches de **convolution** pour extraire des caractéristiques de l'image et produit une probabilité en sortie.

### Fonctionnement
Le générateur et le discriminateur sont entraînés simultanément dans un processus compétitif :
- Le générateur essaie de produire des images qui trompent le discriminateur.
- Le discriminateur essaie de mieux distinguer les images réelles des images générées.

---

## Installation

Pour exécuter ce notebook, vous aurez besoin des dépendances suivantes :

- Python 3.10
- TensorFlow
- Keras
- NumPy
- Matplotlib
- tqdm

Vous pouvez installer ces dépendances en utilisant pip :

```bash
pip install tensorflow keras numpy matplotlib tqdm
```

---

## Utilisation

1. **Téléchargement des données** : Le notebook commence par charger un ensemble de données d'images d'anime à partir d'un répertoire spécifié. Assurez-vous que les images sont correctement organisées dans le répertoire `/kaggle/input/anime-faces/data`.

2. **Préparation des données** : Les images sont chargées et prétraitées pour être utilisées comme entrées pour le modèle. Cela inclut le redimensionnement des images et la normalisation des valeurs de pixels.

3. **Construction du modèle** :
   - **Generator** : Construit un modèle qui génère des images à partir de bruit aléatoire.
   - **Discriminator** : Construit un modèle qui distingue les images réelles des images générées.
   - **DCGAN** : Combine le générateur et le discriminateur pour former le modèle GAN.

4. **Entraînement du modèle** : Le modèle est entraîné sur les images d'anime. Le processus d'entraînement peut prendre un certain temps, en fonction de la puissance de calcul disponible.

5. **Génération d'images** : Une fois le modèle entraîné, le générateur peut être utilisé pour générer de nouvelles images de visages d'anime.

6. **Visualisation des résultats** : Les images générées sont visualisées à l'aide de Matplotlib.

---

## Structure du projet

- `anime-generator.ipynb` : Le notebook Jupyter contenant tout le code pour charger les données, construire et entraîner le modèle DCGAN, et générer des images.
- `/kaggle/input/anime-faces/data` : Répertoire contenant les images d'anime utilisées pour l'entraînement.

---

## Dépendances

- **TensorFlow** : Bibliothèque de machine learning utilisée pour construire et entraîner le modèle.
- **Keras** : API de haut niveau pour TensorFlow, utilisée pour simplifier la construction de modèles de réseaux de neurones.
- **NumPy** : Bibliothèque pour le calcul numérique en Python.
- **Matplotlib** : Bibliothèque pour la visualisation de données en Python.
- **tqdm** : Bibliothèque pour afficher des barres de progression.

---

## Licence

Ce projet est sous licence MIT. Vous êtes libre de l'utiliser, de le modifier et de le distribuer selon les termes de la licence.

