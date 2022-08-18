# Différents mondes
* Information actif est plus important.
* 2 fins :
  - Tenue de dossiers opérationnels
    - On introduit des données
    - Conserve l'état le plus récent
    - S'occupe d'1 transaction à la fois
  - Prise de décision analytique
    - DW/BI on extrait les données
    - Évaluer la performance
    - S'occupe souvent de plusieurs transactions
    - Requête optimisé pour grand nb de données, dans une perspective historique				
* Encore des DW/BI qui sont de simple copie de données opérationnelles, or besoin spécifiques : performance…
# Rôles de DW BI
- Rend l'information facilement accessible
  - Données intuitives pour utilisateur
  - Structures et libellés imitent les processus de pensées et vocabulaires de l'entreprise
  - Renvoie résultat requête rapide
- Informations cohérentes, crédibles
  - Soigneusement assemblées et nettoyées
  - Libellés et définitions communes
- S'adapte aux changements
  - Sans invalidation de données ou d'applications existantes.
- En temps voulu
  - Données brutes en informations exploitables en heures, minutes, secondes
  - Délais réalistes, surtout si nettoyages
- Protège les informations
  - Ce que l'on vend et à qui sont des données sensibles
  - Contrôle les accès aux informations confidentielles
- Base fiable pour améliorer la prise de décision
  - Décisions basées sur des pruves analytiques
  - Apporte de la valeur ajoutée à l'entreprise
  - Vous concevez un système d'aide à la décision
- Doit être adopté par le monde des affaires
  - Un système opérationnel est obligatoire, pas un syst-me DW/BI
  - Adoption si la source du DW BI est simple et rapide
  On a un pied dans la zone de confort (TI) et un autre dans le terrain peu familier des utilisateurs professionnels (DBA/MBA hybride)
# Métaphore de publication pour les gestionnaires DW/BI [intégral]
- Comprendre les utilisateurs métier
  - Comprendre leurs responsablités, buts et objectifs
  - Déterminer les décisions qu'ils veulent prendre avecle systèem DW/BI
  - Identifier les "meilleurs" utilisateurs qui prennent des décisions efficaces et à fort impact
  - Trouver de nouveaux utilisateurs potentiels et les sensibiliser aux capacités du système DW/BI
-  Fournir des informations et des analyses de haute qualité, pertinentes et accessibles aux utilisateurs professionnels 
  - Choisissez les données les plus robustes et les plus exploitables à présenter dans le système DW/BI, soigneusement sélectionnées dans le vaste univers de sources de données possibles dans votre organisation. 
  - Rendre les interfaces utilisateur et les applications simples et basées sur des modèles, explicitement adaptées aux profils de traitement cognitif des utilisateurs
  - Assurez-vous que les données sont exactes et fiables, en les étiquetant de manière cohérente dans toute l’entreprise
  - Surveiller en permanence l’exactitude des données et des analyses
  - S’adapter à l’évolution des profils d’utilisateurs, des exigences et des priorités de l’entreprise, ainsi qu’à la disponibilité de nouvelles sources de données
- Soutenir l’environnement DW/BI
  - Prendre une partie du crédit pour les décisions commerciales prises à l’aide du système DW/BI et utiliser ces succès pour justifier la dotation en personnel et les dépenses en cours
  - Mettre à jour régulièrement le système DW/BI
  - Maintenir la confiance des utilisateurs professionnels
  - Gardez les utilisateurs professionnels (...) et la direction informatique satisfaits
# Introduction à la modélisation dimensionnelle (DM)
Largement accepté comme technique préférée pour présenter des données analytiques car 2 exigences simultanées :
1. Fournir des données compréhensibles par l'utilisateur métier
1. Fournir des preformances de requêtes rapides
> Technique de longue date, qui permet de simplifier les bases de données.
La capacité à visualiser quelque chose d'aussi abstrait qu'un ensemble de données de façon concrète et tangible est le secret de la compréhensibilité.
Même si les modèles dimentionnels sont instanciés dans SGBDR, sont très différents des modèles 3NF (3 formes normales). 3NF divisent les données en entités discrètes, devenant des tables relationnelles. 1 commamnde d'un produit = 1 ligne dans une table = diagrame complexe en toile dareignée de centaines de tables normalisés.
ERD (diagramme entité-relation) sont des dessins qui schématisent les relations entre les tables.
3NF et DM peuvent être représentés en ERD, la différence étant le *degré de normalisation*. 