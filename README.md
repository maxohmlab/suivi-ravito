# Suivi Ravito

**Suivi Ravito** est un outil de planification et de suivi de la nutrition à l'entraînement et en course. Il aide à préparer une stratégie de ravitaillement, à suivre les apports réellement consommés et à comparer le plan à l'exécution.

Application : https://maxohmlab.github.io/suivi-ravito/

## Fonctionnalités

### Nutrition
- Calcul des apports en glucides (CHO), sodium et caféine.
- Comparaison des apports avec les objectifs définis.
- Calcul des quantités et du rythme de prise à partir des produits sélectionnés.
- Bibliothèque de produits personnalisable.

### Séances planifiées et réalisées
- Création de séances planifiées et enregistrement des apports réellement consommés.
- Association d'une séance réalisée à sa séance planifiée.
- Comparaison planifié/réalisé pour analyser l'exécution.
- Calcul des indicateurs réels à partir des quantités consommées et des caractéristiques actuelles des produits.

### Gestion de plusieurs plans — V2.13
Suivi Ravito permet de conserver plusieurs cycles de préparation au sein du même compte, avec **un seul plan actif à la fois**.

- **Plan actif :** plan utilisé pour préparer les prochaines séances ; les séances et paramètres sont modifiables.
- **Archiver un plan :** clôturer un cycle sans supprimer son historique.
- **Créer un nouveau plan :** démarrer un cycle distinct avec son propre nom, sa course cible et sa date.
- **Consulter un plan archivé :** sélectionner un ancien cycle pour consulter ses séances, statistiques, graphique et résultats en lecture seule.
- **Séparation des historiques :** les séances planifiées et réalisées restent associées à leur plan. Consulter une archive ne change pas le plan actif.
- **Bibliothèque commune :** les produits restent disponibles d'un plan à l'autre.

Les plans archivés sont destinés à la consultation : les séances ne doivent pas y être modifiées ni recevoir de nouvelles entrées.

### Graphique et progression
- Visualisation des séances planifiées et réalisées.
- Identification visuelle des séances planifiées et réalisées.
- Suivi de l'exécution au fil du temps et comparaison avec la cible.

### Partage et données
- Génération d'un résumé copiable pour Strava.
- Export des données.
- Authentification et stockage des données via Supabase.

## Principes de fonctionnement
- **Planifier → Exécuter → Comparer → Ajuster.**
- Les produits sont conservés dans une bibliothèque commune.
- Les séances enregistrent les références produit et les quantités. Les valeurs nutritionnelles sont recalculées à partir de la fiche produit actuelle et ne sont pas figées dans chaque séance.
- Les données de chaque plan restent séparées pour faciliter l'analyse des cycles de préparation.

## Documentation
- [`CHANGELOG.md`](CHANGELOG.md) : historique des versions.
- [`TODO.md`](TODO.md) : pistes pour V3 et les versions suivantes.

## Déploiement
L'application est une page HTML hébergée sur GitHub Pages et utilise Supabase pour l'authentification et la persistance des données. Une configuration Supabase valide est nécessaire pour exécuter l'application.
