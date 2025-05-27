# Projet-Data-Mining
# 🛳️ Classification des Passagers du Titanic – Projet de Data Mining

## 👩‍💻 Auteur
Imane Lahoucik

---

## 🎯 Objectif

Ce projet vise à tester deux méthodes de classification supervisée afin de prédire la survie des passagers du Titanic.  
L’objectif est de classer chaque passager dans l’une des catégories suivantes :
- `1` : Survivant
- `0` : Non survivant

---

## 📊 Données utilisées

Les données proviennent du célèbre dataset Titanic de Kaggle.  
Elles comprennent :

- Identifiant du passager
- Classe du billet
- Nom, genre, âge
- Nombre de frères/sœurs/conjoints à bord
- Nombre de parents/enfants à bord
- Numéro du billet, tarif payé
- Numéro de la cabine
- Port d’embarquement (C = Cherbourg, Q = Queenstown, S = Southampton)
- Statut de survie (`Survived`)

---

## 🧹 Nettoyage & Prétraitement

- Imputation de l’âge manquant par la moyenne selon la classe (`Pclass`)
- Suppression de la variable `Cabin` trop incomplète
- Suppression des colonnes `Name` et `Ticket`
- Encodage des variables catégorielles (ex: `Sex`, `Embarked`)
- Création de variables indicatrices (`get_dummies`)
- Suppression des doublons
- Découpage en train/test : 70% / 30%

---

## 📈 Analyse exploratoire

- Analyse univariée des distributions (`Survived`, `Pclass`, `Sex`, `Age`, etc.)
- Visualisations : countplots, histogrammes, boxplots, heatmaps
- Corrélation entre variables numériques et `Survived`
- Analyse bivariée : proportion de survie selon les catégories

---

## 🧠 Méthodes utilisées

### 1. Régression Logistique
- Modèle construit avec `statsmodels.Logit`
- Résultats significatifs : `Sex`, `Pclass`, `Age`
- Accuracy : **81.65%**

### 2. Arbre de Décision
- Optimisation de la profondeur avec validation croisée
- Meilleure performance obtenue avec profondeur `3`
- Accuracy : **78.65%**
- Analyse de l’importance des variables

---

## 🥇 Conclusion

La **régression logistique** s’est révélée légèrement plus performante que l’arbre de décision dans ce contexte (82% vs 78.6%).  
Elle permet une meilleure généralisation sur les données de test pour prédire la survie des passagers selon des caractéristiques socio-démographiques.

---

## 🛠️ Librairies utilisées

```python
pandas, numpy, seaborn, matplotlib  
scikit-learn, statsmodels
