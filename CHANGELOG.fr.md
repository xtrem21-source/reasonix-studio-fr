# Journal des modifications

Toutes les évolutions notables de ce projet sont documentées ici.

Le format suit [Keep a Changelog](https://keepachangelog.com/fr/1.1.0/), et ce projet
respecte le [versionnage sémantique](https://semver.org/lang/fr/).

Le numéro de version suit celui de Reasonix Studio en amont qu'il empaquette.

La version anglaise de ce fichier est `CHANGELOG.md`.

---

## [2.50-fr] — 2026-10-24

Première version française publiée de **Reasonix Studio 2.50.0** pour Windows x64.
C'est une œuvre dérivée du projet amont, distribuée sous sa licence MIT ; voir
`LICENSE`.

### Ajouté

- **Interface entièrement française**, 5 047 libellés traduits, livrée sous forme
  d'un dossier prêt à l'emploi : sans installateur, sans entrée de registre, sans
  droit administrateur.
- **Micro de dictée intégré** : un bouton micro dans la zone de saisie du chat, le
  choix du fournisseur, et un repli automatique quand un fournisseur échoue.
- `README.md` (anglais) et `README.fr.md` (français), tous deux précisant ce qui a
  été modifié par rapport à l'amont, la limite connue, et ce que la licence impose.
- `reasonix-studio-2.50-fr.zip` (193 Mo) publiée comme élément de release.
  L'exécutable amont pèse 234 Mo, au-delà de la limite de 100 Mo par fichier que
  GitHub applique aux arborescences — l'élément de release est la seule façon
  conforme de le distribuer.

### Modifié

- **Trois fichiers de l'interface sont modifiés** par rapport à l'amont, tous sous
  `resources\frontend-next\dist\` : le bundle i18n (dictionnaire français, `fr`
  accepté, détection automatique forcée en `fr`), le bundle Settings (« Français »
  ajouté au sélecteur de langue), et `index.html` (charge le module micro).
- **La détection automatique de la langue répond désormais `fr`.** Sans cela, le
  français ne tient pas en 2.50 : l'application remet son réglage de langue à vide
  au démarrage et retombe en détection automatique.

### Problèmes connus

- **Le sélecteur de langue n'est pas persistant.** Choisir l'anglais dans les
  réglages est écrasé au démarrage suivant. En pratique, l'interface reste en
  français.
- Deux libellés des réglages, `Ask` et `MCP · Skills`, restent non traduits : leurs
  chaînes sources ont changé en 2.50 et ne correspondent plus au dictionnaire.
- La cause première de la remise à zéro de la langue n'est pas identifiée. Elle se
  trouve probablement dans l'exécutable hôte, ce qui explique qu'elle soit
  contournée plutôt que corrigée.

### Notes de mise à jour

- N'acceptez pas les mises à jour proposées par l'application : elles écrasent les
  fichiers traduits et retirent le micro. Chaque version amont demande une nouvelle
  release ici.
- Les releases précédentes de ce dépôt sont conservées ; rien n'est supprimé.
