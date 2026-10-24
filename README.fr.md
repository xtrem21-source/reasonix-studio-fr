# Reasonix Studio FR

<p align="center"><img src="assets/logo.png" width="128" alt="Reasonix Studio FR"></p>


**Une version française de Reasonix Studio, prête à l'emploi, avec un micro de dictée intégré.**

Ce dépôt publie la version recompilée en français de **Reasonix Studio** — l'application
desktop du projet [**DeepSeek-Reasonix**](https://github.com/esengine/DeepSeek-Reasonix) —
pour que personne n'ait à patcher quoi que ce soit après l'installation.

> **Non officiel.** Ce projet n'est ni affilié à, ni approuvé par, ni sponsorisé par le
> projet DeepSeek-Reasonix (Reasonix Studio) ni par ses mainteneurs.

Le travail de traduction lui-même — dictionnaire, scripts, outillage — vit dans son
propre dépôt : [**Reasonix-Traduction-Fr**](https://github.com/xtrem21-source/Reasonix-Traduction-Fr).
Ce dépôt-ci ne livre que le résultat.

La documentation existe en français (`README.fr.md`, `CHANGELOG.fr.md`) et en
anglais (`README.md`, `CHANGELOG.md`).

---

## Ce qu'il contient

| Élément | Détail |
|---|---|
| Reasonix Studio | **2.50.0**, Windows x64, tel que publié en amont |
| Interface | **5 047 libellés traduits**, langue automatique forcée en français |
| Micro | dictée intégrée à la zone de saisie, choix du fournisseur, repli automatique |
| Conditionnement | un simple dossier — sans installateur, sans entrée de registre, sans droit administrateur |

## Installation

1. télécharger `ReasonixStudio-windows-amd64-fr.zip` depuis la page **Releases** ;
2. dézipper où vous voulez (par exemple `J:\Reasonix Studio`) ;
3. lancer `Reasonix Studio.exe`.

Pour la retirer, supprimez le dossier. Rien d'autre n'a été écrit.

> L'archive est publiée en tant qu'élément de release, pas en commit : `Reasonix Studio.exe`
> pèse 234 Mo et GitHub refuse tout fichier de plus de 100 Mo dans une arborescence.

## Ce qui a été modifié par rapport à l'amont

Trois fichiers de l'interface web, sous `resources\frontend-next\dist\` :

| Fichier | Modification |
|---|---|
| `assets\i18n-<empreinte>.js` | dictionnaire français, `fr` accepté comme langue, détection automatique forcée en `fr` |
| `assets\Settings-<empreinte>.js` | « Français » ajouté au sélecteur, trois libellés traduits |
| `index.html` | chargement du module micro |

Le module micro (`voice-input.js`) est un ajout : il n'existe pas en amont.

Les noms de fichiers portent une empreinte de compilation qui change à chaque version.
Les scripts ne les codent pas en dur — ils lisent `index.html` pour trouver le bundle
réellement chargé.

## Limite connue

Le sélecteur de langue des réglages **n'est pas persistant**. Reasonix Studio 2.50 remet
son réglage de langue à vide au démarrage et retombe en détection automatique. Le français
tient parce que la détection a été forcée, pas parce que le choix est respecté. En pratique,
l'interface est toujours en français.

## Mises à jour

**N'acceptez pas les mises à jour proposées par l'application.** Elles écrasent les fichiers
traduits et retirent le micro. Chaque version amont demande une nouvelle release ici.

| Version | État |
|---|---|
| 2.50.0 | publiée |

## Licence et attribution

Reasonix Studio est publié sous **licence MIT** par **esengine**. Cette distribution est
une œuvre dérivée : la licence MIT et la mention de copyright de l'amont s'appliquent, et
sont reproduites dans `LICENSE`.

Aucune garantie n'est fournie, ni par l'amont, ni ici.

