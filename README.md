# Reasonix Studio FR — version complète, français intégré

Version **prête à installer** de [Reasonix Studio](https://github.com/esengine/DeepSeek-Reasonix)
en français, avec un **micro de dictée** intégré.

Pas de patch à lancer. On télécharge l'archive de la release, on dézippe, on
lance. L'interface s'ouvre en français.

---

## Ce qu'il y a dedans

| Élément | Détail |
|---|---|
| Reasonix Studio | **2.50.0**, Windows x64, tel que publié par l'amont |
| Interface | **5 047 libellés traduits**, langue automatique forcée en français |
| Micro | dictée intégrée à la fenêtre de chat, avec choix du fournisseur et repli automatique |
| Données | restent sur le disque de votre choix ; aucune n'est écrite pendant la préparation |

## Installation

1. télécharger `reasonix-studio-2.50-fr.zip` depuis la page **Releases** ;
2. dézipper où vous voulez (par exemple `J:\Reasonix Studio`) ;
3. lancer `Reasonix Studio.exe`.

Aucun installateur, aucun droit administrateur, aucune écriture dans le registre :
c'est une copie de dossier, elle se supprime comme un dossier.

> L'archive dépasse la limite de 100 Mo par fichier imposée à l'arborescence Git :
> c'est pourquoi le binaire est distribué en **release**, et non dans les commits.

---

## Ce qui a été modifié par rapport à l'amont

Trois fichiers de l'interface, dans `resources\frontend-next\dist\` :

| Fichier | Modification |
|---|---|
| `assets\i18n-<empreinte>.js` | dictionnaire français + langue `fr` acceptée + auto-détection forcée en `fr` |
| `assets\Settings-<empreinte>.js` | « Français » ajouté au sélecteur, trois libellés traduits |
| `index.html` | chargement du module micro |

Le module micro (`voice-input.js`) est un ajout : il n'existe pas en amont.

Le détail des modifications, les scripts et les dictionnaires sont dans le dépôt
compagnon : [`reasonix-fr-patch`](https://github.com/xtrem21-source/reasonix-fr-patch).

---

## Limite connue

Le sélecteur de langue des réglages **n'a pas d'effet durable** : l'application
remet son réglage à vide au démarrage. Le français tient parce que l'auto-détection
a été forcée, pas parce que le choix est respecté. En pratique : l'interface sera
en français, quel que soit le réglage.

---

## Mises à jour

**N'installez pas les mises à jour proposées par l'application** : elles
remplaceraient les fichiers francisés et retireraient le micro. Chaque nouvelle
version amont demande une nouvelle release ici.

| Version | État |
|---|---|
| 2.50.0 | publiée |

---

## Licence et attribution

Reasonix Studio est publié sous **licence MIT** par **esengine**.
Cette distribution est un dérivé : la licence MIT et la mention de copyright de
l'amont s'appliquent, et sont reproduites dans `LICENSE`.

Aucune garantie n'est fournie, ni par l'amont, ni ici.
