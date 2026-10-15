# CHANGELOG — Suivi Ravito

Historique des versions et principales évolutions du projet.

## [V2.13] — 2026-10-15

### Gestion des plans
- Gestion de plusieurs plans de préparation, avec un seul plan actif par utilisateur.
- Possibilité d'archiver le plan actif et de démarrer un nouveau cycle.
- Consultation des plans archivés en lecture seule.
- Le changement de plan actualise les séances, les statistiques, le graphique et les paramètres affichés.
- Les séances planifiées et réalisées restent rattachées à leur plan d'origine.

### Aide et documentation
- Mise à jour de l'onglet « Aide » pour expliquer la gestion des plans.
- Documentation complétée sur l'archivage, la création et la consultation des plans.

## [V2.12.1] — 2026-09-07
### Correctifs
- Correction de la modification des quantités dans une séance planifiée : la nouvelle quantité est conservée lors de l'édition.

## [V2.12] — 2026-09-02
### Authentification
- Amélioration de l'écran de connexion.
- Correction de la redirection après confirmation d'e-mail avec `emailRedirectTo`.
- Stabilisation de l'authentification Supabase sur GitHub Pages.
### Suivi des séances
- Calcul et sauvegarde des valeurs `actual_*` des séances réalisées.
- Synchronisation après chargement et modification des produits.
- Liaison séance réalisée / séance planifiée via `linked_plan_id`.
### Graphique et interface
- Affichage conjoint des séances planifiées et réalisées.
- Cercles distincts pour les points planifiés et réalisés, ligne d'exécution et ligne cible.
- Moyenne d'exécution calculée uniquement sur les séances réalisées liées à un plan.
- Axe temporel basé sur les dates réelles.
- Amélioration de l'écran d'accueil et du footer.
- Export des données.

## [V2.11] — 2026-08
- Corrections du graphique de progression.
- Amélioration de la gestion planifiée / réalisée.
- Amélioration de l'affichage de l'authentification et de l'accueil.

## [V2.1] — 2026-08
- Ajout du nom du plan, du nom de la course et de la date de course au profil.
- Sauvegarde des paramètres de plan dans Supabase.
- Ajout/utilisation des champs `actual_cho_per_hour`, `actual_sodium_per_hour` et `actual_caffeine_per_hour`.
- Liaison séance réalisée / planifiée avec `linked_plan_id`.
- Export des données.
- Les séances stockent les références produit et les quantités, sans snapshot nutritionnel.

## [V2.0] — 2026-08
- Première intégration de Supabase, authentification et persistance des données.
- Création des tables `profiles`, `products`, `session_products` et `sessions`.

## V1 — Prototype initial
- Outil HTML autonome de planification et de suivi du ravitaillement.
- Calcul des glucides, du sodium et de la caféine, calculateur rapide et horaires de prise.
- Bibliothèque de produits, suivi planifié / réalisé et graphique de progression.
- Résumé copiable pour Strava et export/import JSON dans le prototype initial.
- Déploiement initial sur GitHub Pages ; version historique conservée sous `index-v1.html`.
