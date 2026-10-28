# Répertoire documentaire Culture

Application web statique de consultation de **67 ressources documentaires**, issues du Genially « Bases données MC » de la Mission de la politique documentaire (MPDOC), ministère de la Culture.

## Fonctionnalités

- Cartes et affichage en liste.
- Recherche dans les intitulés, descriptions, organismes et catégories, avec ou sans accents.
- Filtres par domaine et par disponibilité d’une adresse actuelle.
- Descriptions originales intégrales dans les fiches.
- Liens actuels, liens historiques et résultats de comparaison avec la liste officielle.
- Export CSV de l’inventaire et téléchargement du rapport d’analyse.
- Interface adaptée aux écrans mobiles et navigation au clavier.

## Lancement local

Aucune installation ni compilation n’est nécessaire. Avec Python 3 :

```bash
python -m http.server 8000 --directory dist
```

Ouvrir ensuite `http://localhost:8000` dans un navigateur. L’application peut aussi être ouverte directement via `dist/index.html`.

## Structure

```text
dist/
  index.html       Page principale
  styles.css       Mise en forme et adaptation mobile
  app.js           Recherche, filtres, cartes et fiches
  data.js          Données des 67 ressources
  Inventaire_Bases_Donnees_MC.csv
  Rapport_Analyse_Bases_Donnees_MC.md
```

## Mise à jour des données

Modifier les objets du tableau `window.RESOURCES` dans `dist/data.js`. Chaque objet conserve un identifiant, un intitulé, la description originale, les catégories, l’organisme mentionné, les adresses originale et actuelle et les observations. Actualiser la date de contrôle affichée dans l’interface et les exports lorsque les données sont à nouveau vérifiées.

## Provenance et limites

- Source : https://view.genially.com/5eb120f294fd8d0d87dec7ef
- Liste officielle comparée : https://www.culture.gouv.fr/rechercher-une-publication-du-ministere-de-la-culture/bases-de-donnees
- Date du contrôle documentaire : **28 octobre 2026**.

Les 69 occurrences du Genially sont regroupées en 67 ressources distinctes, en conservant les associations aux catégories. Les descriptions historiques ne sont pas reformulées. Une adresse actuelle peut désigner une notice institutionnelle ou un portail : sa disponibilité ne garantit pas celle de chaque fonction du service cible. Les liens de service non contrôlés sont identifiés dans les fiches. Les données ne sont pas actualisées automatiquement.

Le rapport inclus détaille la méthode et les limites de vérification. Cette application de travail n’est pas présentée comme un site officiel du ministère de la Culture. La publication du code ne vaut pas attribution d’une licence aux textes des organismes cités.

## Déploiement

Publier le contenu de `dist/` sur un hébergement statique. Aucun secret, compte de service ou serveur applicatif n’est nécessaire. Les polices Google sont facultatives ; des polices de repli sont prévues.
