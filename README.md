# 📸 Traitement d'Images avec OpenCV et Python

Ce projet explore les techniques fondamentales de traitement d'images en utilisant OpenCV et Python. Il couvre les filtres de lissage, les opérations morphologiques et diverses transformations d'images.

## 📋 Table des matières

- [🚀 Installation](#-installation)
- [📁 Structure du projet](#-structure-du-projet)
- [🔧 Fonctionnalités](#-fonctionnalités)
- [📖 Notebooks](#-notebooks)
- [🎯 Exemples d'utilisation](#-exemples-dutilisation)
- [📚 Concepts abordés](#-concepts-abordés)
- [🛠️ Prérequis](#️-prérequis)
- [🤝 Contribution](#-contribution)

## 🚀 Installation

### Prérequis
- Python 3.12.11
- Environnement conda/venv configuré

### Installation des dépendances
```shell script
pip install opencv-python matplotlib numpy pillow ipython jupyter
```


### Packages installés
- `opencv-python` - Traitement d'images
- `matplotlib` - Visualisation
- `numpy` - Calculs numériques
- `pillow` - Manipulation d'images
- `ipython` - Interface interactive
- `jupyter` - Notebooks interactifs

## 📁 Structure du projet

```
basic_img_proc_op/
├── images/
│   ├── radeau.jpg
│   └── opencv_morphological_ops_pyimagesearch_logo.png
├── bilateral.ipynb          # Filtres bilatéraux
├── convolution.ipynb        # Opérations morphologiques
└── README.md               # Ce fichier
```


## 🔧 Fonctionnalités

### 🎨 Filtres de lissage
- **Filtre bilatéral** : Lissage intelligent préservant les contours
- Réduction du bruit tout en gardant les détails importants
- Paramètres ajustables pour différents effets

### 🔍 Opérations morphologiques
- **Érosion** : Réduction des objets clairs
- **Dilatation** : Expansion des objets clairs
- **Ouverture** : Érosion suivie de dilatation
- **Fermeture** : Dilatation suivie d'érosion
- **Gradient morphologique** : Détection de contours
- **Top Hat** : Extraction d'éléments clairs sur fond sombre
- **Black Hat** : Extraction d'éléments sombres sur fond clair

## 📖 Notebooks

### 1. `bilateral.ipynb`
Exploration du filtre bilatéral avec :
- Comparaison de différents paramètres
- Analyse des effets sur diverses images
- Visualisation des résultats

### 2. `convolution.ipynb`
Démonstration des opérations morphologiques :
- Érosion et dilatation avec différentes itérations
- Opérations combinées (ouverture, fermeture)
- Effets de différentes tailles de noyaux
- Applications pratiques

## 🎯 Exemples d'utilisation

### Filtre bilatéral
```python
import cv2
import matplotlib.pyplot as plt

# Charger l'image
image = cv2.imread('images/radeau.jpg')

# Appliquer le filtre bilatéral
filtered = cv2.bilateralFilter(image, 15, 50, 50)

# Afficher les résultats
plt.figure(figsize=(12, 6))
plt.subplot(1, 2, 1)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))
plt.title('Original')
plt.axis('off')

plt.subplot(1, 2, 2)
plt.imshow(cv2.cvtColor(filtered, cv2.COLOR_BGR2RGB))
plt.title('Filtre bilatéral')
plt.axis('off')
plt.show()
```


### Opérations morphologiques
```python
# Conversion en niveaux de gris
gray = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)

# Érosion
eroded = cv2.erode(gray, None, iterations=2)

# Dilatation
dilated = cv2.dilate(gray, None, iterations=2)

# Ouverture
kernel = cv2.getStructuringElement(cv2.MORPH_RECT, (5, 5))
opened = cv2.morphologyEx(gray, cv2.MORPH_OPEN, kernel)
```


## 📚 Concepts abordés

### 🔄 Filtre bilatéral
- **Principe** : Filtrage spatial + filtrage colorimétrique
- **Avantages** : Préservation des contours, réduction du bruit
- **Applications** : Retouche photo, preprocessing
- **Paramètres** :
  - `diameter` : Taille du voisinage
  - `sigmaColor` : Sensibilité aux différences de couleur
  - `sigmaSpace` : Influence de la distance spatiale

### 🧮 Morphologie mathématique
- **Éléments structurants** : Formes définissant les opérations
- **Opérations de base** : Érosion, dilatation
- **Opérations combinées** : Ouverture, fermeture
- **Applications** : Nettoyage d'images, détection de formes

### 🎨 Visualisation
- Conversion d'espaces colorimétriques (BGR ↔ RGB)
- Affichage côte à côte pour comparaison
- Utilisation de matplotlib pour la visualisation

## 🛠️ Prérequis

### Connaissances requises
- Bases de Python
- Notions de traitement d'images
- Utilisation des notebooks Jupyter

### Environnement technique
- **OS** : macOS Sonoma (aarch64)
- **IDE** : DataSpell 2025.1.2
- **Python** : 3.12.11
- **Gestionnaire de paquets** : conda/venv

## 🚦 Démarrage rapide

1. **Cloner le projet**
```shell script
git clone <repository-url>
cd basic_img_proc_op
```


2. **Installer les dépendances**
```shell script
pip install -r requirements.txt
```


3. **Lancer les notebooks**
```shell script
jupyter notebook
```


4. **Ouvrir les fichiers**
- `bilateral.ipynb` pour les filtres bilatéraux
- `convolution.ipynb` pour les opérations morphologiques

## 📝 Notes importantes

### ⚠️ Gestion des couleurs
- OpenCV utilise le format BGR
- Matplotlib utilise le format RGB
- Toujours convertir avec `cv2.cvtColor()` pour l'affichage

### 🔧 Optimisation
- Le filtre bilatéral est coûteux en calcul
- Les opérations morphologiques sont plus rapides
- Tester différents paramètres selon l'image

### 📊 Bonnes pratiques
- Sauvegarder les images originales
- Documenter les paramètres utilisés
- Comparer les résultats visuellement

## 🤝 Contribution

Les contributions sont les bienvenues ! Pour contribuer :

1. Forkez le projet
2. Créez une branche pour votre fonctionnalité
3. Commitez vos changements
4. Poussez vers la branche
5. Ouvrez une Pull Request

## 📄 License

Ce projet est sous licence MIT. Voir le fichier LICENSE pour plus de détails.

---

**Développé avec ❤️ en utilisant OpenCV et Python**

*Pour toute question ou suggestion, n'hésitez pas à ouvrir une issue !*
