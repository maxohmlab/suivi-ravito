# Suivi Ravito

Outil web pour planifier et suivre les apports en **glucides, sodium et caféine** lors des sorties longues et des courses — gels, boissons isotoniques, gommes, pastilles de sel, etc.

Pensé pour le **gut training** : progresser semaine après semaine sur le débit de glucides (g/h) toléré à l'effort, comparer systématiquement ce qui était *prévu* à ce qui a été *réellement pris*, et générer un timing de prise réaliste pour le jour de la course.

La version actuelle utilise **Supabase** pour l'authentification et la sauvegarde des données. L'application reste une page HTML autonome côté interface et peut être publiée sur **GitHub Pages**.

> Version 2.1 : connexion utilisateur, profil personnel, bibliothèque de produits et séances sauvegardées dans Supabase.

---

## Sommaire

- [Fonctionnalités](#fonctionnalités)
- [Démarrage rapide](#démarrage-rapide)
- [Guide des onglets](#guide-des-onglets)
- [Bibliothèque de produits](#bibliothèque-de-produits)
- [Exemples de calcul](#exemples-de-calcul)
- [Données et sauvegarde](#données-et-sauvegarde)
- [Structure technique](#structure-technique)
- [Avertissement](#avertissement)
- [Auteur](#auteur)

---

## Fonctionnalités

- **Calcul en direct** : glucides (g et g/h), sodium (mg et mg/h), caféine (mg) à partir des produits et quantités choisis.
- **Jauge visuelle** : pourcentage d'exécution par rapport à une cible CHO/h, avec code couleur (vert / orange / rouge).
- **Calculateur rapide** : combien d'un produit donné faut-il pour atteindre une cible CHO/h sur une durée donnée.
- **Plan de prise automatique** : un timing de prise différent selon la catégorie de produit (voir [Exemples de calcul](#exemples-de-calcul)).
- **Séances planifiées vs réalisées** : bascule une prévision en séance réalisée sans perdre la prévision d'origine — comparaison produit par produit générée automatiquement.
- **Graphique de progression** : CHO/h réalisé vs cible, sur un vrai axe temporel (les dates, pas juste l'ordre des séances), exportable en PNG.
- **Résumé Strava en un clic** : texte prêt à coller (avec emojis) résumant les apports et les produits d'une séance réalisée.
- **Bibliothèque de produits** : produits de référence partagés et produits personnalisés par utilisateur, avec nom, catégorie, unité, glucides, sodium, caféine et remarque.
- **Compte utilisateur** : connexion par email/mot de passe et profil personnel.
- **Sauvegarde automatique** : produits, séances et paramètres du profil sont sauvegardés dans Supabase.
- **Export JSON** : export local des données du compte pour disposer d'une copie personnelle.

---

## Démarrage rapide

**Option 1 — en local**
L'ancienne version sans gestion de profil et sauvegarde est toujours disponible avec le fichier `index-v1.html`. Ouvre-le directement dans ton navigateur (double-clic). Aucune installation, aucun serveur.

**Option 2 — sur GitHub Pages**
La nouvelle version v2.1 est accessible ici : `https://maxohmlab.github.io/suivi-ravito/index.html`.

Ajoute la page à l'écran d'accueil de ton téléphone (Safari/Chrome → "Ajouter à l'écran d'accueil") pour un accès rapide façon application.

---

## Guide des onglets

### Séance
Formulaire de saisie : type (Prévision / Réalisé), semaine (ex. `S5`), date, durée, cible CHO/h, produits et quantités. Les résultats (jauge, totaux, plan de prise) se recalculent en direct.

### Planifiées
Liste de toutes les séances de type "Prévision". Le jour J : ouvre la séance via **Modifier**, ajuste les quantités réellement prises, bascule le type sur **Réalisé**, enregistre. La prévision d'origine reste dans cet onglet ; une nouvelle séance apparaît dans l'Historique avec un comparatif Prévu → Réalisé.

### Historique
Liste des séances "Réalisé", triées de la plus récente à la plus ancienne. Chaque séance affiche sa jauge d'exécution, ses produits, et — si elle provient d'une conversion — son comparatif Prévu → Réalisé. Bouton **📋 Copier pour Strava** sur chaque séance.

### Graphique
Courbe CHO/h réalisé vs cible, sur un axe X proportionnel aux **dates réelles** (pas un simple emplacement par séance — un écart de deux semaines entre deux sorties se voit visuellement comme deux fois plus large qu'un écart d'une semaine). Point plein = réalisé, point creux = prévision, couleur du point = même code que la jauge. Export en PNG.

### Aide
Mode d'emploi condensé, exemple de progression "gut training" sur 12 semaines et points de vigilance produits. Les données sont désormais sauvegardées automatiquement dans le compte ; l'onglet propose uniquement l'export JSON.

---

## Bibliothèque de produits

12 produits par défaut, basés sur des fiches produit officielles (Decathlon, Tā Energy) :

| Produit | Format | Glucides | Sodium | Caféine | Catégorie |
|---|---|---|---|---|---|
| ISO+ Decathlon (neutre) | dose (500 ml) | 33 g | 285 mg | 0 mg | Hydratation |
| ISO+ Decathlon (menthe) | dose (500 ml) | 33 g | 372 mg | 0 mg | Hydratation |
| Decathlon pastille de sel | gélule | 0 g | 118 mg | 0 mg | Électrolytes |
| TA Energy gel (normal) | gel (40 ml) | 33 g | 50 mg | 0 mg | Gels |
| TA Energy gel (salé) | gel (40 ml) | 33 g | 100 mg | 0 mg | Gels |
| TA Energy gel (CAF) | gel (40 ml) | 33 g | 50 mg | 50 mg | Gels |
| Decathlon Energy Gel+ | gel (46 g / 35 ml) | 30 g | 70 mg | 0 mg | Gels |
| Decathlon Gel 1:0.8 | gel (45 ml) | 40 g | 100 mg | 0 mg | Gels |
| TA Energy gommes (normal) | sachet (3 gommes) | 24 g | 114 mg | 0 mg | Gommes |
| TA Energy gommes (salé) | sachet (3 gommes) | 24 g | 228 mg | 0 mg | Gommes |
| TA Energy gommes (CAF) | sachet (3 gommes) | 24 g | 114 mg | 50 mg | Gommes |
| TA Energy gommes (CAF renforcée) | sachet (3 gommes) | 24 g | 114 mg | 100 mg | Gommes |

Catégories disponibles pour les produits personnalisés : **Hydratation, Électrolytes, Gels, Gommes, Barres, Compotes, Autres**. La catégorie n'est pas qu'un rangement : elle pilote directement le comportement du Plan de prise (voir plus bas).

Les produits de référence sont partagés en lecture. Les produits personnels peuvent être modifiés ou supprimés par leur propriétaire.

---

## Exemples de calcul

### 1. Débit CHO/h et jauge

Séance de **2h50** (170 min), avec **2 doses ISO+** (33 g CHO chacune) et **3 gels TA Energy normal** (33 g CHO chacun) :

```
Total CHO   = 2×33 + 3×33            = 165 g
Durée       = 170 min = 2,83 h
CHO/h       = 165 ÷ 2,83             = 58,2 g/h
```

Avec une cible de **50 g/h** :

```
% de la cible = 58,2 ÷ 50 × 100 = 116 %
→ zone orange (écart modéré au-dessus de la cible)
```

Code couleur de la jauge :

| % de la cible | Couleur | Signification |
|---|---|---|
| 95 – 115 % | 🟢 vert | dans la cible |
| 80 – 95 % ou 115 – 140 % | 🟠 orange | écart modéré |
| < 80 % ou > 140 % | 🔴 rouge | hors cible |

### 2. Sodium

Même séance :

```
Total Na = 2×285 (ISO+ neutre) + 3×50 (TA Energy gel) = 720 mg
Na/h     = 720 ÷ 2,83                                  = 254 mg/h
```

### 3. Calculateur rapide

Cible **65 g/h** sur **2h** (120 min), avec un seul produit : Gel 1:0.8 (40 g CHO/unité).

```
CHO cible total = 65 × (120/60)        = 130 g
Quantité         = arrondi(130 ÷ 40)    = 3,5 unités
Intervalle        = 120 ÷ 3,5           ≈ 34 min
→ "1 prise toutes les 34 min"
```

### 4. Plan de prise — trois logiques selon la catégorie

**Hydratation** (ex. ISO+) : consigne continue, pas d'horaires ponctuels.
> Départ **0:00** — gorgée toutes les **15 min**. Rythme visé ~1 dose/h → **3** doses recommandées sur 2h50. Si tu as prévu 2 doses : *"complète avec de l'eau si ça ne suffit pas"*.

**Électrolytes** (ex. pastille de sel) : cadence horaire fixe, indépendante des glucides.
> 2 pastilles sur une séance de 2h50 → **1:00**, puis **2:00**.

**Gels / Gommes / Barres / Compotes / Autres** : entrelacement proportionnel, pour éviter que deux prises différentes tombent au même moment.
> 1 Energy Gel+ et 1 Gel 1:0.8 (un seul de chaque) sur 2h50 → au lieu de tomber tous les deux au milieu de la séance, ils sont écartés à **57 min** et **1h53**, selon la formule :
> ```
> t(k) = durée × k / (N + 1)
> ```
> où *N* est le nombre total de prises glucidiques et *k* le rang de la prise dans la séquence (calculée par un algorithme de répartition équitable, pas produit par produit isolément).

### 5. Comparatif Prévu → Réalisé

Prévision : 2× ISO+, 3× TA Energy gel → 165 g CHO
Réalisé : 2× ISO+, 2× TA Energy gel → 132 g CHO

```
Écart = 132 − 165 = −33 g
```

Affiché automatiquement produit par produit dès qu'une prévision est convertie en séance réalisée.

### 6. Résumé Strava généré

```
⚡ Nutrition — S5 · 2h50
🍞 132g glucides (46,6g/h · 93% de la cible)
🧂 520mg sodium (184mg/h)
☕ 50mg caféine

💧 2× ISO+ Decathlon (neutre)
🍯 2× TA Energy gel (normal)
🧂 2× Pastille de sel Decathlon
🍯 1× TA Energy gel (CAF)
```

---

## Données et sauvegarde

La version 2.1 utilise **Supabase** pour stocker les données associées au compte utilisateur.

- **Profil** : nom affiché, nom du plan, nom de la course et date de course.
- **Produits** : bibliothèque de référence partagée et produits personnels.
- **Séances** : prévisions et séances réalisées, avec leurs produits et quantités.
- **Prévu → Réalisé** : une séance réalisée conserve le lien vers sa prévision via `linked_plan_id`.
- **Calculs réalisés** : les valeurs CHO/h, sodium/h et caféine/h sont enregistrées pour les séances réalisées.
- **Export JSON** : permet de conserver une copie personnelle des données du compte.

Les caractéristiques nutritionnelles restent centralisées dans la table des produits : une modification d'un produit peut donc modifier les calculs des séances qui l'utilisent.

## Avertissement

Cet outil est un calculateur et un organisateur de plan de prise — il ne remplace pas un avis médical ou l'accompagnement d'un professionnel de la nutrition sportive. Les valeurs nutritionnelles par défaut proviennent de fiches produit publiques et peuvent évoluer : vérifie-les sur l'emballage si un doute persiste.

---

## Auteur

**Run Un Max**
[substack.com/@maxohm](https://substack.com/@maxohm)

© 2026 · Créé à l'aide de Claude AI
