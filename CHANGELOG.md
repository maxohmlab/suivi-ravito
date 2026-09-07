# CHANGELOG — Suivi Ravito

Historique des versions et principales évolutions.

## [V2.12.1] — 2026-09-07
### Correctifs
- Correction de la modification des quantités dans une séance planifiée.
- La nouvelle quantité est désormais correctement conservée lors de l'édition.

## [V2.12] — 2026-09-02
### Authentification
- Amélioration de l'écran de connexion.
- Correction de la redirection après confirmation d'e-mail avec `emailRedirectTo`.
- Stabilisation de l'authentification Supabase sur GitHub Pages.

### Suivi des séances
- Calcul et sauvegarde des valeurs `actual_*` des séances réalisées.
- Synchronisation après chargement et modification des produits.
- Liaison séance réalisée / séance planifiée via `linked_plan_id`.

### Graphique
- Affichage conjoint des séances planifiées et réalisées.
- Planifiée : cercle vide.
- Réalisée : cercle plein.
- Ligne reliant les séances réalisées liées à un plan.
- Ligne cible en pointillés.
- Moyenne d'exécution calculée uniquement sur les séances réalisées liées à un plan.
- Axe temporel basé sur les dates réelles.

### Interface
- Amélioration de l'écran d'accueil et du footer.
- Conservation du lien vers Run Un Max.
- Export des données.

## [V2.11] — 2026-08
### Correctifs
- Corrections du graphique de progression.
- Amélioration de la gestion planifiée / réalisée.
- Amélioration de l'affichage de l'authentification et de l'accueil.

## [V2.1] — 2026-08
### Données et Supabase
- Ajout du nom du plan, nom de la course et date de course au profil.
- Sauvegarde des paramètres de plan dans Supabase.
- Ajout/utilisation des champs `actual_cho_per_hour`, `actual_sodium_per_hour` et `actual_caffeine_per_hour`.
- Liaison séance réalisée / planifiée avec `linked_plan_id`.
- Export des données.

### Produits
- Les caractéristiques restent dans la bibliothèque produit.
- Les séances stockent les références produit et les quantités, sans snapshot nutritionnel.

## [V2.0] — 2026-08
### Première intégration Supabase
- Passage du prototype autonome à une architecture Supabase.
- Ajout de l'authentification.
- Persistance des données.
- Création des tables `profiles`, `products`, `session_products` et `sessions`.

## V1 — Prototype initial
### Fonctionnalités
- Outil HTML autonome de planification et suivi du ravitaillement.
- Calcul des glucides, sodium et caféine.
- Indicateur par rapport à l'objectif glucides.
- Calculateur rapide.
- Génération automatique des horaires de prise.
- Bibliothèque de produits.
- Suivi planifié / réalisé.
- Graphique de progression.
- Résumé copiable pour Strava.
- Export/import JSON.

### Déploiement
- Première publication via GitHub Pages.
- Version historique conservée sous `index-v1.html`.
