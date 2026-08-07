# Architecture — Boussole

Version documentée : **1.0.0**  
Fichier principal : `boussole.html`

## 1. Vue d’ensemble

**Boussole** est une application web autonome contenue dans un fichier HTML unique.

Elle ne nécessite :
- aucun serveur ;
- aucune installation ;
- aucune bibliothèque JavaScript externe ;
- aucun framework ;
- aucune base de données.

Le fichier `boussole.html` regroupe la structure HTML, les styles CSS, la logique JavaScript, l’interface bilingue et les styles d’impression.

## 2. Organisation générale

```text
boussole.html
├── <head>
│   ├── métadonnées
│   ├── favicon
│   └── <style>
│       ├── variables graphiques
│       ├── titraille
│       ├── structure et formulaires
│       ├── actions
│       ├── footer
│       ├── responsive
│       └── impression / PDF
├── <body>
│   └── application
│       ├── en-tête
│       ├── switch FR / EN
│       ├── formulaire
│       │   ├── A — Titre et thème
│       │   ├── B — Destinataire
│       │   ├── C — Support
│       │   ├── D — Objectif
│       │   ├── E — Message principal
│       │   ├── F — Effet attendu
│       │   ├── G — Ton
│       │   ├── H — Informations indispensables
│       │   └── I — À écarter
│       ├── actions d’export/import
│       ├── feuille d’impression générée
│       └── footer Eigrutel BD Academy
└── <script>
    ├── données et valeurs par défaut
    ├── internationalisation
    ├── sauvegarde locale
    ├── gestion des sections
    ├── export Markdown
    ├── export/import JSON
    ├── génération de la feuille d’impression
    └── gestion de l’interface
```

## 3. Données

Les champs du formulaire sont identifiés par l’attribut `data-field`.

Les valeurs sont regroupées dans un objet JavaScript correspondant à la fiche courante. La structure reste indépendante de la langue de l’interface : changer FR / EN ne modifie pas le texte saisi par l’utilisateur.

Principaux champs :
- `titreHistoire`
- `theme`
- `destinataire`
- `support`
- `formatLecture`
- `objectifPrincipal`
- `enjeuNarratif`
- `promesseLecture`
- `ideeImportante`
- `uneChose`
- `infoPremiere`
- `comprendreApres`
- `ressentirApres`
- `erreurEviter`
- `tonPrincipal`
- `faits`
- `personnages`
- `lieux`
- `objets`
- `references`
- `echos`
- `alourdirait`
- `autreHistoire`
- `implicite`
- `digression`

## 4. Stockage local

L’application utilise `localStorage` pour conserver :
- le contenu courant de la fiche ;
- l’état ouvert ou fermé des sections ;
- la langue d’interface choisie.

Le français est la langue utilisée lors de la première ouverture. Le choix effectué ensuite est mémorisé dans le navigateur.

Aucune donnée n’est envoyée vers un serveur.

## 5. Internationalisation

L’interface dispose de deux langues :
- français ;
- anglais.

Le changement de langue agit sur les éléments d’interface : titres, rubriques, labels, placeholders, boutons, messages, libellés d’impression et export Markdown.

Le contenu saisi par l’utilisateur n’est jamais traduit automatiquement.

## 6. Sections repliables

Chaque groupe du formulaire est une section `.boussole-section`.

Le bouton `.section-toggle` ajoute ou retire la classe `is-collapsed`. L’état des sections est enregistré dans `localStorage`.

## 7. Redimensionnement des zones de texte

Les éléments `<textarea>` adaptent automatiquement leur hauteur au contenu afin de limiter les barres de défilement internes.

Le recalcul est effectué lors de la saisie et lors des changements d’affichage utiles.

## 8. Export JSON

L’export JSON produit une copie portable des données de la fiche.

Le fichier contient notamment :
- l’identification de l’application ;
- la version ;
- la date d’export ;
- les données du formulaire.

L’import JSON recharge les données dans les champs correspondants.

## 9. Export Markdown

La fonction d’export Markdown reconstruit la fiche sous forme de document texte structuré :
- titre ;
- sections ;
- libellés ;
- réponses.

Les libellés suivent la langue active de l’interface.

## 10. Impression et PDF

Le bouton d’export PDF utilise la fonction d’impression native du navigateur.

Avant impression, une feuille spécifique est générée dans `#printSheet`.

Les règles `@media print` :
- masquent l’interface interactive ;
- affichent uniquement la feuille d’impression ;
- utilisent une mise en page A4 ;
- répartissent les rubriques dans une présentation compacte.

La création effective du PDF dépend du navigateur ou du système d’exploitation.

## 11. Responsive

Une media query adapte l’interface aux écrans étroits.

Sur mobile :
- la grille à deux colonnes passe à une colonne ;
- les marges sont réduites ;
- les boutons occupent plus facilement la largeur disponible.

## 12. Dépendances

Aucune dépendance logicielle externe.

Le seul élément externe prévu par l’interface est le lien du footer vers le site Eigrutel BD Academy.

Le favicon est chargé depuis :

```text
favicon/fav14.png
```

Il doit donc être conservé dans cette arborescence lors de la publication.

## 13. Vie privée

Boussole ne comporte :
- aucun compte utilisateur ;
- aucun système d’analyse d’audience intégré ;
- aucune publicité ;
- aucun suivi ;
- aucune transmission automatique des contenus saisis.

Les données restent dans le navigateur jusqu’à leur suppression ou leur export volontaire.

## 14. Points à vérifier avant une nouvelle version stable

Avant publication :
1. vérifier l’interface française ;
2. vérifier l’interface anglaise ;
3. vérifier la persistance de la langue ;
4. tester l’ouverture et la fermeture des neuf sections ;
5. tester la sauvegarde automatique ;
6. tester l’export JSON ;
7. réimporter le JSON exporté ;
8. tester l’export Markdown dans les deux langues ;
9. tester l’impression / PDF ;
10. vérifier l’affichage ordinateur, tablette et téléphone ;
11. vérifier Safari, Firefox et les navigateurs Chromium disponibles ;
12. mettre à jour le numéro de version et `CHANGELOG.md`.

## 15. Licence et attribution

Code : **GNU AGPL v3.0 ou version ultérieure**.

Documentation et modèles : **CC BY-SA 4.0**, sauf mention contraire.

Les marques, logos et signes distinctifs **Eigrutel**, **Eigrutel Lab** et **Eigrutel BD Academy** sont réservés.

Programme conçu et développé par **Simon Léturgie** dans le cadre d’**Eigrutel BD Academy** et d’**Eigrutel Lab — Atelier d’outils libres pour la bande dessinée**.
