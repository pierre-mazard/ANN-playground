# Perceptron Multicouches (PMC)

## 1. Intoduction

Le Perceptron Multicouches (PMC), également appelé Multilayer Perceptron (MLP), est un réseau de neurones artificiels composé de plusieurs couches de neurones interconnectés. Il constitue l’un des fondements historiques du Deep Learning moderne.

Contrairement au perceptron simple, limité aux problèmes linéairement séparables, le PMC est capable d’apprendre des relations complexes et non linéaires grâce à l’utilisation de plusieurs couches cachées et de fonctions d’activation.

Les PMC sont utilisés pour des tâches de classification, de régression, de reconnaissance de motifs et de prédiction.

## 2. Architecture du PMC

Un Perceptron Multicouches est composé de plusieurs couches de neurones organisées de manière séquentielle.

Entrée → Couche cachée(s) → Sortie

Chaque neurone d'une couche est généralement connecté à tous les neurones de la couche suivante.

### 2.1 Couche d'entrée

La couche d'entrée reçoit les caractéristiques (features) du jeu de données.

Exemple :

    * âge
    * moyenne générale
    * nombre d'absences

Chaque caractéristique correspond à un neurone d'entrée.

### 2.3 Couches cachées

Les couches cachées réalisent les transformations intermédiaires permettant au réseau d'apprendre des relations complexes.

Chaque neurone calcule :

z = Wx + b

puis applique une fonction d'activation.

### 2.4 Couche de sortie

La couche de sortie produit la prédiction finale.

Classification binaire : 1 neurone + Sigmoid

Classification multiclasse : N neurones + Softmax

Régression : 1 neurone linéaire

## 3. PMC pour la calssification et la régression 

Le choix de l'architecture dépend du type de problème.

### 3.1 Classification 

La classification consiste à prédire une catégorie. 

Exemple : 

    * Spam / Non Spam
    * Résussite / Échec
    / Chat / Chien 

Fonctions généralement utilisées : 

    * ReLU dans les couches cachées
    * Softmax ou Sigmoid en sortie

Loss : 

    * Binary Cross Entropy
    * Categorical Cross Entropy 

### 3.2 Régression 

La régression consiste à prédure une valeure numérique continue. 

Exemples : 

    * Prix immobilier
    * Température
    * Chiffre d'affaires

Fonction de sortie : 
    
    * Linéraire

Loss : 

    * Mean Squared Error

## 4. Fonciton d'activation 

Les fonctions d'activation permettent d'introduire de la non-linéarité dans le réseau de neurones.
Sans elles, un PMC composé de plusieurs couches serait équivalent à une simple régression linéaire.

Elles déterminent comment les informations sont transformées et propagées à travers le réseau.

### 4.1 Sigmoid

La fonction Sigmoid transforme une valeur réelle en une valeur comprise entre 0 et 1. 

f(x) = 1 / (1 +e^(-x))

Avantages : 

    * Facile à interpréter comme une probabilité.
    * Favorise la phénomène de vanishing gradient. 

### 4.2 Tanh

La foncton Tangente Hyperbolique retourne une valeur comprise entre -1 et 1.

Avantages : 

    * Sorties centrées autour de zéro.
    * Convergence souvent meilleur que Sigmoid.

Incovénients : 

    * Toujours senseible aux vanishig gradient. 

### 4.3 ReLU

Rectified Linear Unit : 

f(x) = max(0,x)

Avantages :

    * Trs raoude à calculer.
    * Réduit le vanishing gradient. 
    * Fcontion la plus utilisée aujourdh'ui.

Inconvénients : 

    * Risque de neurones morts lorsque les sorties restent constamments négatives. 

### 4.4 Leaky ReLU

Variante de ReLU permettant une faible pente pour les valeurs négatives afin de réduire le phénomène de neurones morts.

### 4.5 Softmax

La fonction Sostmax converti un vectur de valeurs en probabilité.

La somme de sprobabilités est égale à 1.

ELle est principalement utilisée dans les problèmes de calssification multicalsse.

## 5. Propagation avant
La propagation avant consiste à faire circuler les données d'entrées à travers les différentes couches du réseau afind 'obtenir une prédiction.

Pour cahque neurone : 

z= W.x + b

où :

    * W représente les poids
    * x représentes les entrées
    * b représente le biais

Une fonction d'actiaition est ensuite appliquée : 

a = f(z)

Le résultat est transmis à la couche suivante jusqu'a la couche de sortie. 

Exemple : 

Entrée : 

    * âge
    * absences
    * moyenne

    ↓

    Couche cachée

    ↓ 

    Couche cachée

    ↓ 

    Prédiction : Dropout / Graduate / Enrolled

## 6. Rétropropagation

## 7. Fonction de parte

## 8. Descente de gradient

## 9. Vanishing Gradient

## 10. Hyperparamètres

## 11. Bonnes pratiques

## 12. Conclusion 