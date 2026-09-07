# TODO — Suivi Ravito

## V3 — Fonctionnalités prévues

### Priorité 1 — Objectif sodium personnalisé
- [ ] Ajouter un objectif de sodium/h personnalisé.
- [ ] Permettre de définir cet objectif à partir du profil de sudation.
- [ ] Prendre en compte la température prévue / les conditions de course.
- [ ] Afficher clairement l'objectif sodium/h dans le plan.
- [ ] Comparer le sodium réellement consommé à l'objectif.

### Priorité 2 — Bibliothèque de produits publics
- [ ] Permettre aux utilisateurs de partager certains produits.
- [ ] Créer une bibliothèque publique de produits.
- [ ] Distinguer clairement produits personnels et publics.
- [ ] Prévoir validation/modération et gestion des doublons.
- [ ] Permettre à chaque utilisateur de conserver ses produits personnels.

### Priorité 3 — Analyse planifié vs réalisé
- [ ] Étendre l'analyse aux glucides, sodium et caféine.
- [ ] Afficher les écarts entre objectif et consommation réelle.
- [ ] Conserver la logique : **Planifier → Exécuter → Comparer → Ajuster**.

### Profil de course
- [ ] Ajouter un profil de course plus complet.
- [ ] Renseigner les caractéristiques utiles à la stratégie nutritionnelle.
- [ ] Utiliser ces informations pour contextualiser les objectifs.

### Progression / suivi
- [ ] Améliorer les indicateurs de progression.
- [ ] Mettre en évidence la régularité d'exécution.
- [ ] Conserver le graphique planifié/réalisé actuel comme base.

### Météo / conditions
- [ ] Étudier une intégration météo pour adapter notamment le sodium.
- [ ] Privilégier une recommandation simple et compréhensible.
- [ ] Ne pas rendre l'intégration obligatoire si elle complexifie l'outil.

### Ravitos de course / apports complémentaires
- [ ] Envisager une note qualitative pour les aliments pris en complément.
- [ ] Exemple : « quelques morceaux de pastèque au ravitaillement ».
- [ ] Ne pas obliger à quantifier précisément les apports inconnus.
- [ ] Ne pas intégrer automatiquement ces apports approximatifs dans le CHO/h.
- [ ] Distinguer produits planifiés/suivis et apports complémentaires.

### Partage / visibilité
- [ ] Ajouter le lien Suivi Ravito dans « Copier pour Strava ».
- [ ] Utiliser une URL en clair.
- [ ] Exemple : `🔗 Planifié avec Suivi Ravito : https://maxohmlab.github.io/suivi-ravito/`

## Principes à conserver
- [ ] Garder l'outil simple et rapide.
- [ ] Ne pas transformer Suivi Ravito en outil de comptabilité alimentaire exhaustive.
- [ ] Prioriser les données utiles à la préparation et à l'exécution.
- [ ] Ne pas forcer la quantification des aliments pris aux ravitaillements.
- [ ] Conserver les caractéristiques des produits dans leur fiche, sans snapshot historique.
- [ ] Conserver la logique planifié → réalisé.
- [ ] Éviter les fonctionnalités sociales ou prédictives trop complexes.

## À évaluer avant développement
- [ ] Prioriser les fonctionnalités selon les premiers retours utilisateurs.
- [ ] Évaluer la valeur réelle de l'intégration météo.
- [ ] Définir le modèle de données de la bibliothèque publique.
- [ ] Définir les règles de validation/modération.
- [ ] Définir le contenu d'un éventuel profil de course.
