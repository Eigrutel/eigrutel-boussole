# Changelog

Toutes les modifications notables de **Boussole** seront documentées dans ce fichier.

Le format s’inspire de [Keep a Changelog](https://keepachangelog.com/fr/1.1.0/) et le projet utilise une numérotation de version de type [Semantic Versioning](https://semver.org/).

## [Unreleased]

### Prévu
- Corrections et évolutions futures après retour d’usage.
## [1.0.1] — 2026-08-16

### Corrigé / Fixed

* Correction de la perte des données lors de l’utilisation de Boussole comme webapp sur iOS et iPadOS.
* Fixed data loss when Boussole is used as an iOS/iPadOS web app.
* Renforcement de la persistance locale avec une sauvegarde redondante `localStorage` + `IndexedDB`.
* Improved local persistence with redundant `localStorage` + `IndexedDB` storage.
* Restauration de la sauvegarde la plus récente au démarrage de l’application.
* Restores the most recent saved state when the application starts.
* Suppression de `sessionStorage` du mécanisme de persistance.
* Removed `sessionStorage` from the persistence mechanism.
* Sécurisation de la conservation des données lors des exports JSON et Markdown.
* Improved data preservation during JSON and Markdown exports.

### Technique / Technical

* Demande de stockage persistant via l’API du navigateur lorsqu’elle est disponible.
* Requests persistent browser storage when the API is available.
* Migration compatible avec les données précédemment enregistrées par Boussole.
* Maintains migration compatibility with data previously saved by Boussole.

## [1.0.0] — 2026-08-01

### Ajouté
- Première version stable de **Boussole**.
- Fiche de cadrage pour préparer et orienter une histoire de bande dessinée.
- Neuf sections : titre et thème, destinataire, support, objectif, message principal, effet attendu, ton, informations indispensables et éléments à écarter.
- Sections repliables.
- Sauvegarde automatique locale dans le navigateur.
- Export et import JSON.
- Export Markdown.
- Mise en page dédiée à l’impression et à l’enregistrement PDF.
- Interface responsive pour ordinateur, tablette et téléphone.
- Interface bilingue français–anglais.
- Français utilisé par défaut.
- Switch discret FR / EN.
- Mémorisation locale de la langue sélectionnée.
- Traduction des libellés, placeholders, boutons, messages, impression et export Markdown.
- Application autonome réunie dans un fichier HTML unique, sans bibliothèque externe.

### Licence
- Code : GNU AGPL v3.0 ou version ultérieure.
- Documentation et modèles : CC BY-SA 4.0, sauf mention contraire.
- Marques, logos et signes distinctifs Eigrutel / Eigrutel Lab / Eigrutel BD Academy : réservés.
