# Chapitre 1

## Différents mondes

* Information actif est plus important.
* 2 fins :
  * Tenue de dossiers opérationnels
    * On introduit des données
    * Conserve l'état le plus récent
    * S'occupe d'1 transaction à la fois
  * Prise de décision analytique
    * DW/BI on extrait les données
    * Évaluer la performance
    * S'occupe souvent de plusieurs transactions
    * Requête optimisé pour grand nb de données, dans une perspective historique
* Encore des DW/BI qui sont de simple copie de données opérationnelles, or besoin spécifiques : performance…

## Rôles de DW BI

* Rend l'information facilement accessible
  * Données intuitives pour utilisateur
  * Structures et libellés imitent les processus de pensées et vocabulaires de l'entreprise
  * Renvoie résultat requête rapide
* Informations cohérentes, crédibles
  * Soigneusement assemblées et nettoyées
  * Libellés et définitions communes
* S'adapte aux changements
  * Sans invalidation de données ou d'applications existantes.
* En temps voulu
  * Données brutes en informations exploitables en heures, minutes, secondes
  * Délais réalistes, surtout si nettoyages
* Protège les informations
  * Ce que l'on vend et à qui sont des données sensibles
  * Contrôle les accès aux informations confidentielles
* Base fiable pour améliorer la prise de décision
  * Décisions basées sur des pruves analytiques
  * Apporte de la valeur ajoutée à l'entreprise
  * Vous concevez un système d'aide à la décision
* Doit être adopté par le monde des affaires
  * Un système opérationnel est obligatoire, pas un syst-me DW/BI
  * Adoption si la source du DW BI est simple et rapide
On a un pied dans la zone de confort (TI) et un autre dans le terrain peu familier des utilisateurs professionnels (DBA/MBA hybride)

## Métaphore de publication pour les gestionnaires DW/BI [intégral]

* Comprendre les utilisateurs métier
  * Comprendre leurs responsablités, buts et objectifs
  * Déterminer les décisions qu'ils veulent prendre avecle systèem DW/BI
  * Identifier les "meilleurs" utilisateurs qui prennent des décisions efficaces et à fort impact
  * Trouver de nouveaux utilisateurs potentiels et les sensibiliser aux capacités du système DW/BI

* Fournir des informations et des analyses de haute qualité, pertinentes et accessibles aux utilisateurs professionnels
* Choisissez les données les plus robustes et les plus exploitables à présenter dans le système DW/BI, soigneusement sélectionnées dans le vaste univers de sources de données possibles dans votre organisation.
* Rendre les interfaces utilisateur et les applications simples et basées sur des modèles, explicitement adaptées aux profils de traitement cognitif des utilisateurs
* Assurez-vous que les données sont exactes et fiables, en les étiquetant de manière cohérente dans toute l’entreprise
* Surveiller en permanence l’exactitude des données et des analyses
* S’adapter à l’évolution des profils d’utilisateurs, des exigences et des priorités de l’entreprise, ainsi qu’à la disponibilité de nouvelles sources de données
* Soutenir l’environnement DW/BI
  * Prendre une partie du crédit pour les décisions commerciales prises à l’aide du système DW/BI et utiliser ces succès pour justifier la dotation en personnel et les dépenses en cours
  * Mettre à jour régulièrement le système DW/BI
  * Maintenir la confiance des utilisateurs professionnels
  * Gardez les utilisateurs professionnels (...) et la direction informatique satisfaits

## Introduction à la modélisation dimensionnelle (DM)

Largement acceptée comme technique préférée pour présenter des données analytiques, car 2 exigences simultanées :

1. Fournir des données compréhensibles par l'utilisateur métier
1. Fournir des performances de requêtes rapides

> Technique de longue date, qui permet de simplifier les bases de données.

La capacité à visualiser quelque chose d'aussi abstrait qu'un ensemble de données de façon concrète et tangible est le secret de la compréhensibilité.

Même si les modèles dimensionnels sont instanciés dans SGBDR, sont très différents des modèles 3NF (3 formes normales). 3NF divise les données en entités discrètes, devenant des tables relationnelles.  
1 commande d'un produit = 1 ligne dans une table = diagramme complexe en toile d'areignée de centaines de tables normalisées.

ERD (diagramme entité-relation) sont des dessins qui schématisent les relations entre les tables.
3NF et DM peuvent être représentés en ERD, la différence étant le **degré de normalisation**.

3NF est utile pour le traitement opérationnel, car une transaction impacte un seul endroit.

Les modèles normalisés :

1. Sont trop complexes pour :

* comprendre
* navigueur
* se souvenir

du modèle, qui ressemble à une carte du métro parisien [au système d'autoroute de Los Angeles]

1. Nécessitent des requêtes trop complexes et peu performantes

1. Exposent une utilisation peu intuitive de la aone de présentation.

> Un modèle dimensionnel contient les mêmes informations qu’un modèle normalisé, mais empaquette les données dans un format qui offre à l’utilisateur une compréhensibilité, des performances de requête et une résilience aux modifications

## Schéma en étoile vs cubes OLAP

Modèle dimensionnels :

* dans SGBRD = schéma en étoile
* dans environnements de base de données multidimensionnelles = OLAP (cubes de traitement analytique en ligne)

![Schéma en étoile vs cubes OLAP](https://2.bp.blogspot.com/-WpSy-JrsL0k/XGhI8r_svwI/AAAAAAAAHAA/WH9XVgXIPqA-iYgcMU_5DVgViuWWpdT5wCLcBGAs/s1600/star_cube.jpg)

Si votre environnement DW/BI exploitent schéma en étoile et cube OLAP :

* dimensions reconnaissables
* mise en oeuvre physique différente

Quand les données sont chargés dans cube OLAP :

* stockées et indexées à l’aide de formats et de techniques conçus pour les données dimensionnelles
* offrent des performances de requête supérieures grâce aux précalculs, aux stratégies d'indexation et d'autres optimisations
* forages vers le bas ou vers le haut en ajoutant ou en supprimant des attributs de l'analyses avec d'excellentes performances sans émettre de nouvelles requêtes
* fournissent également des fonctions plus robustes et analytiques qui dépassent celles disponibles avec SQL

Inconvénient : performance de charge pour ces fonctionnalités, en particulier avec de grands ensembles de données
