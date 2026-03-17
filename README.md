# Analyse du Comportement Client sur une Plateforme E-commerce

Ce projet a pour objectif d'analyser le comportement des clients et les tendances de ventes sur une plateforme e-commerce française de C2C (consumer-to-consumer) spécialisée dans la mode. L'analyse est réalisée via une application web interactive qui s'appuie sur une API Flask pour les calculs statistiques.

**Source des données :** [E-Commerce Users of a French C2C Fashion Store (Kaggle)](https://www.kaggle.com/datasets/jmmvutu/ecommerce-users-of-a-french-c2c-fashion-store)

## Technologies Utilisées

- **Backend :** Python, Flask, Pandas, SciPy
- **Frontend :** HTML, CSS, JavaScript
- **Base de données :** MySQL / MariaDB (via phpMyAdmin)

---

## Guide d'Installation et de Lancement

Suivez ces étapes pour configurer et lancer le projet sur votre machine locale.

### 1. Prérequis

- **Python 3 :** Assurez-vous que Python 3 est installé sur votre système.
- **Serveur de base de données :** Un serveur comme WAMP, MAMP, XAMPP ou autre, avec **phpMyAdmin** fonctionnel.

### 2. Configuration de la Base de Données

1.  Démarrez votre serveur Apache et MySQL.
2.  Ouvrez **phpMyAdmin**.
3.  Créez une nouvelle base de données (par exemple, `datamoodbd`).
4.  Sélectionnez la base de données que vous venez de créer, puis allez dans l'onglet **Importer**.
5.  Importez le fichier `datamoodbd.sql` fourni dans le projet.

### 3. Configuration de l'Environnement Python

Ouvrez un terminal dans le répertoire racine du projet (`gestion_projet_L3_miashs`).

**a. Créez un environnement virtuel :**
```bash
python -m venv .venv
```

**b. Activez l'environnement virtuel :**

-   **Sur Windows (Invite de commandes / PowerShell) :**
    ```cmd
    .venv\Scripts\activate
    ```
-   **Sur macOS / Linux :**
    ```bash
    source .venv/bin/activate
    ```
*(Une fois activé, le nom de l'environnement `(.venv)` devrait apparaître au début de la ligne de votre terminal.)*

**c. Installez les dépendances :**
Naviguez dans le dossier `dataMood` et installez les paquets requis.
```bash
cd dataMood
pip install -r requirements.txt
cd ..
```

### 4. Lancement de l'Application

**a. Démarrez le serveur API :**
Assurez-vous que l'environnement virtuel est toujours activé.
```bash
python dataMood/exploitation_data/api_server.py
```
Le terminal devrait indiquer que le serveur est en cours d'exécution (`Running on http://127.0.0.1:5000`).

**b. Ouvrez le site web :**
Naviguez vers le dossier `dataMood/exploitation_data/web` et ouvrez le fichier `index.html` dans votre navigateur web. L'application est maintenant prête à être utilisée.

# DataMood - Description de la Plateforme SaaS Analytics

##  Aperçu du Projet

**DataMood** est une plateforme SaaS analytics développée dans le cadre d'un projet de L3 MIASHS. L'application permet aux entreprises de comprendre et analyser le comportement de leurs clients à travers des comparaisons de données détaillées entre 2020 et 2024.

###  Objectif Global
Créer une plateforme SaaS analytics permettant aux entreprises de mieux cibler, segmenter et personnaliser leurs stratégies commerciales basées sur des insights data réels.

##  Le Problème Résolu

Les entreprises ont accès à beaucoup de données (genre, pays, plateforme, historique d'achat, followers, etc.) mais ne savent pas comment les analyser efficacement pour en tirer des conclusions utiles.

**Exemples de questions auxquelles DataMood répond :**
- "Est-ce que les femmes achètent plus sur mobile que sur web ?"
- "Avoir beaucoup de followers signifie vraiment avoir plus de ventes ?"
- "Est-ce qu'une photo de profil augmente vraiment les ventes ?"
- "Quel pays est le plus actif en 2024 comparé à 2020 ?"

Sans cet outil, répondre à ces questions demande expertise technique + temps + coûts élevés.

##  La Solution

Un dashboard interactif en **2 modes d'accès** :

###  Mode GRATUIT (Accès Standard)
L'utilisateur accède à des comparaisons pré-définies avec :
- Visualisations automatiques
- Chiffres et pourcentages clés
- Conclusions pré-rédigées et compréhensibles

**Comparaisons incluses :**
- Évolution 2020 vs 2024 (genre, pays, langue)
- Top 5 pays les plus actifs
- Genre dominant de la plateforme
- Taux d'adoption des applications mobiles
- Impact de la photo de profil sur les ventes

###  Mode PAYANT (Accès Personnalisé)
L'utilisateur peut créer sa propre analyse :
- Sélectionne 2 variables à comparer (ex: Genre vs Taux d'achat)
- Génération automatique d'un graphique adapté à la corrélation
- Analyse statistique détaillée
- Conclusion claire et actionnable

##  Source des Données

Base de données multi-tables contenant :

**Données Principales**
- Identité : ID unique, genre (M/F), pays, langue, titre
- Type : Vendeur ou Client
- Profil : Photo, ancienneté du compte, dernière connexion
- Plateforme : Usage Web, Android App, iOS App

**Données Comportementales**
- Wishlist : Articles ajoutés en liste de souhaits
- Likes : Produits aimés
- Achats : Produits effectivement achetés
- Ventes : Produits mis en vente et vendus
- Engagement : Nombre de followers, abonnements

**Données Temporelles**
- 2 snapshots temporels : 2020 et 2024
- Permet une comparaison sur 4 ans du comportement client

##  Utilisateurs Cibles

1. **Propriétaires/Managers d'e-commerce**
   - Comprendre leurs clients
   - Décisions marketing/produit basées sur des données

2. **Consultants/Data Analysts**
   - Créer des rapports sans coder
   - Visualiser des insights pour leurs clients

3. **Growth Hackers**
   - Rechercher des corrélations cachées
   - Optimiser l'acquisition et la rétention

##  Les 6 Axes d'Analyse Principaux

1. **Comparaison Temporelle** (2020 vs 2024)
   - Évolution du genre dominant, pays actifs, comportement d'achat

2. **Analyse Géographique**
   - Top pays, différences comportementales par région

3. **Comportement d'Achat par Genre**
   - Différences femmes/hommes, taux de conversion, taille du panier

4. **Adoption des Plateformes** (Web/Mobile)
   - Performance des plateformes, évolution de l'usage mobile

5. **Le "Profil Parfait" vs Nouveau Profil**
   - Impact photo de profil, ancienneté, connexion régulière

6. **Corrélation Followers ↔ Ventes**
   - Détection d'influenceurs "faux" ou vendeurs "cachés"

##  Modèle Économique

| Mode FREE | Mode PRO |
|-----------|----------|
| Accès aux comparaisons pré-calculées | Comparaisons illimitées |
| Jusqu'à 5 comparaisons/mois | Génération de rapports automatiques |
| Support communautaire | Export PDF/PNG |
| **Gratuit** | **Payant** (selon volume) |

##  Technologies Utilisées

- **Backend API** : Python Flask, SciPy
- **Frontend** : PHP, JavaScript, HTML/CSS
- **Base de données** : MySQL (phpMyAdmin)
- **Data Science** : Pandas, NumPy, Matplotlib
- **Visualisation** : Graphiques dynamiques
- **Outils** : Git/GitHub, Figma, Méthodologie Agile

##  Mon Rôle dans le Projet

**Chef de projet & Développeuse Frontend** (équipe de 4 personnes)

-  Coordination de l'équipe et gestion de projet Agile
-  Développement des interfaces frontend
-  Supervision du dépôt GitHub (gestion des branches, pull requests)
-  Participation à la conception de l'architecture
-  Pivot stratégique de la version C2C vers B2B

##  Résultats et Livrables

-  V1 livrée dans les délais
-  Dashboard FREE fonctionnel avec 6 visualisations pré-définies
-  Mode PRO opérationnel avec authentification
-  API backend pour récupérer et analyser les données
-  Documentation utilisateur et technique

##  Documentation

Consultez le dossier [`/docs`](/docs) pour :
- [Description détaillée du projet](docs/DESCRIPTION%20DU%20PROJET-1.pdf)
- [Rapport final de gestion de projet](docs/gestion_de_projet%20finale-1.pdf)
- [Diapositive de présentation](docs/Diapo_presentation.pdf)

##  Installation et Démarrage

### Prérequis
- Python , php , java , html , css 
- MySQL (phpMyAdmin)

### Étapes d'installation

1. **Cloner le repository**
```bash
git clone https://github.com/lydiamtch/dataMood.git
cd dataMood

# Ensuite continue avec :
python -m venv .venv
source .venv/bin/activate  # Sur Mac/Linux
# .venv\Scripts\activate  # Sur Windows

cd dataMood
pip install -r requirements.txt
cd ..

python dataMood/exploitation_data/api_server.py