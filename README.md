# howtoreadme — Écrire un excellent README GitHub

> Guide de référence, du débutant à l'avancé. Chaque section se lit indépendamment : va directement à ce dont tu as besoin.

**Ce que tu trouveras ici :** comprendre le rôle d'un README, maîtriser Markdown (et ses variantes GitHub), soigner les blocs de code et l'aspect visuel, structurer un README professionnel, partir de templates prêts à copier, puis fiabiliser le tout (liens, secrets, automatisation).

## Comment utiliser ce guide

| Je veux… | Va à… |
| --- | --- |
| Savoir à quoi sert un README | [A. Comprendre un README](#a-comprendre-un-readme) |
| Apprendre la syntaxe Markdown | [B. Les bases de Markdown](#b-les-bases-de-markdown) |
| Bien présenter du code et des commandes | [C. Les blocs de code](#c-les-blocs-de-code) |
| Ajouter badges, captures, GIF, thème sombre | [D. Les éléments visuels](#d-les-éléments-visuels) |
| Savoir quelles sections écrire, et dans quel ordre | [E. Structure d'un README professionnel](#e-structure-dun-readme-professionnel) |
| Copier un modèle et l'adapter | [F. Templates prêts à utiliser](#f-templates-prêts-à-utiliser) |
| Fiabiliser et automatiser | [G. Bonnes pratiques avancées](#g-bonnes-pratiques-avancées) |
| Corriger un README existant | [H. Erreurs courantes](#h-erreurs-courantes) et [I. Checklist finale](#i-checklist-finale) |

**Conventions du guide.**

- Les exemples de Markdown source sont toujours placés dans un bloc **externe** de quatre backticks (ou plus), pour que les backticks internes ne cassent pas l'affichage. Le principe est expliqué en [C.8](#c8-erreurs-de-délimitation-et-backticks-imbriqués).
- Lorsque c'est possible, le **rendu** est affiché juste après le source. Tu le vois donc tel que GitHub le calcule.
- Les valeurs à remplacer sont écrites en `MAJUSCULES` ou entre chevrons : `OWNER`, `REPO`, `<ton-projet>`.
- Les affirmations qui dépendent de services tiers (badges, cartes de statistiques) sont signalées : elles peuvent changer sans préavis.

## Table des matières

- [Comment utiliser ce guide](#comment-utiliser-ce-guide)
- [A. Comprendre un README](#a-comprendre-un-readme)
  - [A.1 À quoi sert un README](#a1-à-quoi-sert-un-readme)
  - [A.2 Dans quels contextes l'utiliser](#a2-dans-quels-contextes-lutiliser)
  - [A.3 README, documentation, wiki : qui fait quoi](#a3-readme-documentation-wiki--qui-fait-quoi)
  - [A.4 Les caractéristiques d'un bon README](#a4-les-caractéristiques-dun-bon-readme)
  - [A.5 Où GitHub affiche le README](#a5-où-github-affiche-le-readme)
- [B. Les bases de Markdown](#b-les-bases-de-markdown)
  - [B.1 Titres](#b1-titres)
  - [B.2 Gras, italique, barré](#b2-gras-italique-barré)
  - [B.3 Paragraphes et sauts de ligne](#b3-paragraphes-et-sauts-de-ligne)
  - [B.4 Citations](#b4-citations)
  - [B.5 Listes ordonnées et non ordonnées](#b5-listes-ordonnées-et-non-ordonnées)
  - [B.6 Liens externes et internes](#b6-liens-externes-et-internes)
  - [B.7 Images et GIF](#b7-images-et-gif)
  - [B.8 Séparateurs](#b8-séparateurs)
  - [B.9 Code inline](#b9-code-inline)
  - [B.10 Blocs de code](#b10-blocs-de-code)
  - [B.11 Blocs de code avec indication du langage](#b11-blocs-de-code-avec-indication-du-langage)
  - [B.12 Tableaux](#b12-tableaux)
  - [B.13 Cases à cocher](#b13-cases-à-cocher)
  - [B.14 Échappement des caractères Markdown](#b14-échappement-des-caractères-markdown)
  - [B.15 HTML compatible avec GitHub](#b15-html-compatible-avec-github)
  - [B.16 Syntaxes GitHub Flavored Markdown (GFM)](#b16-syntaxes-github-flavored-markdown-gfm)
  - [B.17 Notes, alertes et avertissements GitHub](#b17-notes-alertes-et-avertissements-github)
  - [B.18 Autres éléments utiles](#b18-autres-éléments-utiles)
- [C. Les blocs de code](#c-les-blocs-de-code)
  - [C.1 Code inline ou bloc de code](#c1-code-inline-ou-bloc-de-code)
  - [C.2 Pourquoi préciser le langage](#c2-pourquoi-préciser-le-langage)
  - [C.3 Choisir le bon identifiant de langage](#c3-choisir-le-bon-identifiant-de-langage)
  - [C.4 Exemples par langage](#c4-exemples-par-langage)
  - [C.5 Commandes de terminal lisibles](#c5-commandes-de-terminal-lisibles)
  - [C.6 Extraits de configuration](#c6-extraits-de-configuration)
  - [C.7 Mauvais bloc, bon bloc](#c7-mauvais-bloc-bon-bloc)
  - [C.8 Erreurs de délimitation et backticks imbriqués](#c8-erreurs-de-délimitation-et-backticks-imbriqués)
- [D. Les éléments visuels](#d-les-éléments-visuels)
  - [D.1 Badges](#d1-badges)
  - [D.2 Logos et bannières](#d2-logos-et-bannières)
  - [D.3 Aperçu visuel dans le README](#d3-aperçu-visuel-dans-le-readme)
  - [D.4 Captures d'écran et GIF de démonstration](#d4-captures-décran-et-gif-de-démonstration)
  - [D.5 Alignement et dimensions des images](#d5-alignement-et-dimensions-des-images)
  - [D.6 Images hébergées et chemins relatifs](#d6-images-hébergées-et-chemins-relatifs)
  - [D.7 Tableaux de bord de statistiques GitHub](#d7-tableaux-de-bord-de-statistiques-github)
  - [D.8 Séparateurs et mise en page](#d8-séparateurs-et-mise-en-page)
  - [D.9 Emojis](#d9-emojis)
  - [D.10 Accessibilité](#d10-accessibilité)
  - [D.11 Affichage sur mobile](#d11-affichage-sur-mobile)
  - [D.12 Compatibilité avec le thème sombre et clair](#d12-compatibilité-avec-le-thème-sombre-et-clair)
  - [D.13 Les limites de GitHub](#d13-les-limites-de-github)
- [E. Structure d'un README professionnel](#e-structure-dun-readme-professionnel)
  - [E.1 Principe : adapter, ne pas remplir](#e1-principe--adapter-ne-pas-remplir)
  - [E.2 Vue d'ensemble : sections, statut et ordre](#e2-vue-densemble--sections-statut-et-ordre)
  - [E.3 Titre et présentation](#e3-titre-et-présentation)
  - [E.4 Description courte et proposition de valeur](#e4-description-courte-et-proposition-de-valeur)
  - [E.5 Aperçu visuel](#e5-aperçu-visuel)
  - [E.6 Fonctionnalités](#e6-fonctionnalités)
  - [E.7 Démonstration](#e7-démonstration)
  - [E.8 Installation et prérequis](#e8-installation-et-prérequis)
  - [E.9 Configuration et variables d'environnement](#e9-configuration-et-variables-denvironnement)
  - [E.10 Utilisation et exemples](#e10-utilisation-et-exemples)
  - [E.11 Architecture du projet](#e11-architecture-du-projet)
  - [E.12 Technologies utilisées](#e12-technologies-utilisées)
  - [E.13 Commandes disponibles](#e13-commandes-disponibles)
  - [E.14 Tests et qualité](#e14-tests-et-qualité)
  - [E.15 Déploiement](#e15-déploiement)
  - [E.16 Roadmap](#e16-roadmap)
  - [E.17 Contribution](#e17-contribution)
  - [E.18 Licence](#e18-licence)
  - [E.19 Crédits et remerciements](#e19-crédits-et-remerciements)
  - [E.20 FAQ et dépannage](#e20-faq-et-dépannage)
  - [E.21 Contact et liens utiles](#e21-contact-et-liens-utiles)
- [F. Templates prêts à utiliser](#f-templates-prêts-à-utiliser)
  - [F.1 README minimal pour un petit projet](#f1-readme-minimal-pour-un-petit-projet)
  - [F.2 README pour une bibliothèque ou une API](#f2-readme-pour-une-bibliothèque-ou-une-api)
  - [F.3 README pour une application web](#f3-readme-pour-une-application-web)
  - [F.4 README pour un projet open source](#f4-readme-pour-un-projet-open-source)
  - [F.5 README de présentation de profil GitHub](#f5-readme-de-présentation-de-profil-github)
- [G. Bonnes pratiques avancées](#g-bonnes-pratiques-avancées)
  - [G.1 Ancres et navigation interne](#g1-ancres-et-navigation-interne)
  - [G.2 Liens relatifs dans un dépôt](#g2-liens-relatifs-dans-un-dépôt)
  - [G.3 README principal et documentation détaillée](#g3-readme-principal-et-documentation-détaillée)
  - [G.4 Tableaux complexes et limitations](#g4-tableaux-complexes-et-limitations)
  - [G.5 Badges dynamiques](#g5-badges-dynamiques)
  - [G.6 Organisation des assets](#g6-organisation-des-assets)
  - [G.7 Lisibilité et maintenance](#g7-lisibilité-et-maintenance)
  - [G.8 SEO et découverte d'un projet](#g8-seo-et-découverte-dun-projet)
  - [G.9 Internationalisation](#g9-internationalisation)
  - [G.10 Prévention des informations sensibles dans les exemples](#g10-prévention-des-informations-sensibles-dans-les-exemples)
  - [G.11 Compatibilité GitHub](#g11-compatibilité-github)
  - [G.12 Vérification des liens et des images](#g12-vérification-des-liens-et-des-images)
  - [G.13 Automatisation des contrôles](#g13-automatisation-des-contrôles)
- [H. Erreurs courantes](#h-erreurs-courantes)
  - [H.1 README vide ou trop court](#h1-readme-vide-ou-trop-court)
  - [H.2 README excessivement long et désorganisé](#h2-readme-excessivement-long-et-désorganisé)
  - [H.3 Absence d'installation ou d'exemples](#h3-absence-dinstallation-ou-dexemples)
  - [H.4 Mauvaise utilisation des titres](#h4-mauvaise-utilisation-des-titres)
  - [H.5 Blocs de code sans langage](#h5-blocs-de-code-sans-langage)
  - [H.6 Liens cassés](#h6-liens-cassés)
  - [H.7 Images manquantes](#h7-images-manquantes)
  - [H.8 Badges inutiles](#h8-badges-inutiles)
  - [H.9 Informations obsolètes](#h9-informations-obsolètes)
  - [H.10 Commandes non testées](#h10-commandes-non-testées)
  - [H.11 Clés API ou secrets exposés](#h11-clés-api-ou-secrets-exposés)
  - [H.12 Markdown mal formé](#h12-markdown-mal-formé)
  - [H.13 Récapitulatif rapide](#h13-récapitulatif-rapide)
- [I. Checklist finale](#i-checklist-finale)
- [Sources et inspirations](#sources-et-inspirations)


---

## A. Comprendre un README

### A.1 À quoi sert un README

Un README est la **porte d'entrée** d'un projet. C'est le premier fichier que GitHub affiche quand on ouvre un dépôt. En quelques secondes, le lecteur doit pouvoir répondre à quatre questions :

1. **Quoi ?** Que fait ce projet ?
2. **Pourquoi ?** En quoi est-il utile ou différent ?
3. **Comment ?** Comment l'installer et l'utiliser ?
4. **Et ensuite ?** Où trouver de l'aide, comment contribuer, sous quelle licence ?

Un lecteur qui n'a pas de réponse en moins d'une minute quitte la page. Le README sert donc aussi de **vitrine** (portfolio, recrutement, adoption d'une bibliothèque) et de **mémoire** (toi dans six mois, ou un nouveau coéquipier).

### A.2 Dans quels contextes l'utiliser

| Contexte | Rôle du README | Particularité |
| --- | --- | --- |
| Projet personnel / portfolio | Montrer ce que tu sais faire | Aperçu visuel et décisions techniques en avant |
| Bibliothèque / API | Permettre l'adoption en 5 minutes | Installation, exemple minimal, référence d'API |
| Application web ou mobile | Lancer le projet en local, comprendre l'architecture | Prérequis, variables d'environnement, déploiement |
| Projet open source | Attirer et organiser les contributeurs | Contribution, licence, code de conduite, roadmap |
| Projet scolaire ou d'équipe | Expliquer le sujet, les rôles, comment évaluer | Contexte, équipe, instructions de lancement |
| Dossier d'un dépôt (`src/`, `docs/`…) | Expliquer le contenu d'un sous-dossier | GitHub affiche le README du dossier ouvert |
| Profil GitHub | Se présenter | Dépôt spécial `OWNER/OWNER`, voir [F.5](#f5-readme-de-présentation-de-profil-github) |
| Organisation | Présenter l'organisation | Fichier `profile/README.md` du dépôt `.github` de l'organisation |

### A.3 README, documentation, wiki : qui fait quoi

| | README | Documentation (`docs/`, site) | Wiki GitHub |
| --- | --- | --- | --- |
| **Rôle** | Présenter et démarrer | Référence complète et guides | Notes collaboratives, pages libres |
| **Lecteur type** | Quelqu'un qui découvre | Utilisateur ou développeur engagé | Contributeurs réguliers |
| **Longueur** | Courte à moyenne | Illimitée | Illimitée |
| **Versionné avec le code** | Oui | Oui (si dans le dépôt) | Non, c'est un dépôt git séparé |
| **Relu en pull request** | Oui | Oui | Non (modification directe) |
| **Découvrabilité** | Maximale (page d'accueil du dépôt) | Via liens | Onglet Wiki, peu visible |

**Règle pratique :** le README répond à « est-ce que ça me concerne et comment je commence ? ». Dès qu'une section dépasse environ 30 lignes ou ne concerne qu'une partie des lecteurs (référence d'API complète, guide de déploiement détaillé, historique des décisions), **déplace-la dans `docs/`** et garde un lien dans le README. Évite le wiki pour tout ce qui doit rester synchronisé avec le code.

### A.4 Les caractéristiques d'un bon README

| Critère | Ce que ça veut dire |
| --- | --- |
| **Clair** | La première phrase dit ce que fait le projet, sans jargon inutile. |
| **Utile vite** | Un exemple fonctionnel est accessible en moins de deux écrans. |
| **Exact** | Les commandes ont été exécutées sur une machine propre. |
| **Scannable** | Titres cohérents, listes, tableaux, code coloré : on trouve sans tout lire. |
| **Adapté** | Seules les sections utiles à ce projet sont présentes. |
| **Maintenu** | Pas d'information obsolète, pas de lien mort. |
| **Accessible** | Images avec texte alternatif, structure de titres logique, lisible sur mobile. |
| **Sûr** | Aucun secret, aucune donnée personnelle dans les exemples. |

> [!TIP]
> Test des 30 secondes : fais lire ton README à quelqu'un qui ne connaît pas le projet. Demande-lui, après 30 secondes, ce que fait le projet et comment le lancer. S'il hésite, c'est le README qu'il faut corriger, pas le lecteur.

### A.5 Où GitHub affiche le README

GitHub affiche automatiquement le README s'il se trouve dans le dossier `.github`, à la racine du dépôt ou dans `docs`. Si plusieurs existent, l'ordre de priorité est : `.github`, puis la racine, puis `docs`.

Autres points à connaître :

- **Extension et casse :** `README.md` est le standard. `README.rst`, `README.txt` ou `readme.md` sont aussi reconnus, mais `README.md` évite toute surprise.
- **Limite de taille :** le contenu au-delà de **500 KiB** est tronqué à l'affichage.
- **Sommaire automatique :** pour tout fichier Markdown rendu, GitHub génère un plan à partir des titres (icône « Outline » en haut à droite du fichier). Un README bien titré a donc un sommaire gratuit.
- **README de sous-dossier :** ouvrir un dossier affiche son `README.md` sous la liste des fichiers.
- **Profil et organisation :** voir le tableau de [A.2](#a2-dans-quels-contextes-lutiliser).

---

## B. Les bases de Markdown

Markdown est un langage de balisage léger : tu écris du texte avec quelques symboles, et GitHub le transforme en page mise en forme. GitHub utilise **GFM** (GitHub Flavored Markdown), un sur-ensemble de CommonMark qui ajoute tableaux, cases à cocher, texte barré, alertes, etc.

Chaque sous-section suit le même schéma : **utilité**, **source**, **rendu**, **erreurs fréquentes**.

### B.1 Titres

**Utilité :** structurer le document. GitHub s'en sert pour générer le plan latéral et les ancres de liens internes.

````markdown
# Titre de niveau 1 (le nom du projet, une seule fois)
## Titre de niveau 2 (section principale)
### Titre de niveau 3 (sous-section)
#### Niveau 4
##### Niveau 5
###### Niveau 6
````

**Rendu :** six tailles décroissantes, du plus grand (`#`) au plus petit (`######`). Les niveaux 1 et 2 sont soulignés d'un filet sur GitHub.

**Erreurs fréquentes :**

- Oublier l'espace après les `#` : `#Titre` n'est pas un titre, `# Titre` oui.
- Utiliser un titre pour grossir du texte : choisis le niveau d'après la **structure**, pas la taille.
- Sauter de niveau (`##` puis `####`) : les lecteurs d'écran et le plan latéral en pâtissent.
- Mettre plusieurs `#` de niveau 1 : un seul titre principal par README.

### B.2 Gras, italique, barré

**Utilité :** mettre en valeur un mot ou une idée, sans en abuser.

````markdown
**gras**, __gras aussi__
*italique*, _italique aussi_
***gras et italique***
~~barré~~
Du texte avec <sub>indice</sub> et <sup>exposant</sup>.
````

**Rendu :**

**gras**, __gras aussi__  
*italique*, _italique aussi_  
***gras et italique***  
~~barré~~  
Du texte avec <sub>indice</sub> et <sup>exposant</sup>.

**Erreurs fréquentes :**

- Espaces à l'intérieur des marqueurs : `** gras **` ne fonctionne pas, écris `**gras**`.
- Tout mettre en gras : si tout est important, rien ne l'est. Réserve-le aux avertissements et aux termes clés.
- Utiliser `_` au milieu d'un mot (`snake_case_nom`) : écris-le en code inline avec des backticks (voir [B.9](#b9-code-inline)).

### B.3 Paragraphes et sauts de ligne

**Utilité :** aérer le texte. Un **paragraphe** est séparé du suivant par une **ligne vide**. Un simple retour à la ligne dans le fichier `.md` ne crée **pas** de saut dans le rendu.

````markdown
Première ligne du paragraphe,
suite de la même phrase (pas de saut visible).

Nouveau paragraphe après une ligne vide.

Saut de ligne forcé avec une barre oblique inverse :\
cette ligne est en dessous.

Saut de ligne avec la balise HTML :<br>
cette ligne aussi.
````

**Rendu :**

Première ligne du paragraphe,
suite de la même phrase (pas de saut visible).

Nouveau paragraphe après une ligne vide.

Saut de ligne forcé avec une barre oblique inverse :\
cette ligne est en dessous.

Saut de ligne avec la balise HTML :<br>
cette ligne aussi.

Trois syntaxes de saut de ligne existent dans un fichier `.md` : deux espaces en fin de ligne, une barre oblique inverse `\`, ou `<br>`. Préfère `\` ou `<br>` : les espaces de fin de ligne sont invisibles et souvent supprimés par les éditeurs.

**Erreurs fréquentes :** compter sur un simple retour à la ligne, ou écrire des poèmes de dix lignes sans saut forcé. Dans une liste ou un tableau, utilise `<br>`.

### B.4 Citations

**Utilité :** citer un texte, une réponse, ou isoler une remarque.

````markdown
> Une citation sur une ligne.

> Une citation
> sur plusieurs lignes
>
> — Auteur
````

**Rendu :**

> Une citation sur une ligne.

> Une citation
> sur plusieurs lignes
>
> — Auteur

**Erreurs fréquentes :** oublier le `>` sur une ligne intermédiaire (la citation se coupe), ou utiliser une citation pour faire un encadré d'avertissement : préfère les [alertes](#b17-notes-alertes-et-avertissements-github).

### B.5 Listes ordonnées et non ordonnées

**Utilité :** énumérer (puces) ou décrire une procédure (numéros).

````markdown
- Élément avec tiret
- Autre élément
  - Sous-élément (2 espaces d'indentation)
  - Autre sous-élément

1. Première étape
2. Deuxième étape
   1. Sous-étape (3 espaces d'indentation)
3. Troisième étape
````

**Rendu :**

- Élément avec tiret
- Autre élément
  - Sous-élément (2 espaces d'indentation)
  - Autre sous-élément

1. Première étape
2. Deuxième étape
   1. Sous-étape (3 espaces d'indentation)
3. Troisième étape

**Pour mettre un bloc de code dans une liste**, indente-le du même nombre d'espaces que le texte de l'élément :

`````markdown
1. Installe les dépendances :

   ```bash
   npm install
   ```

2. Lance le serveur :

   ```bash
   npm run dev
   ```
`````

**Erreurs fréquentes :**

- Pas de ligne vide avant la liste quand elle suit un paragraphe : selon le contexte, elle n'est pas reconnue.
- Mauvaise indentation : un sous-élément avec un seul espace devient un élément de même niveau.
- Mélanger `-`, `*` et `+` dans une même liste : choisis un seul marqueur.
- Bloc de code non indenté dans une liste : la numérotation redémarre à 1 après le bloc.

### B.6 Liens externes et internes

**Utilité :** renvoyer vers une page web, une autre partie du document, ou un autre fichier du dépôt.

````markdown
[Texte du lien](https://docs.github.com)
[Lien avec infobulle](https://docs.github.com "Documentation GitHub")
<https://docs.github.com>

Lien interne vers une section : [voir l'installation](#installation)
Lien relatif vers un fichier : [guide de contribution](CONTRIBUTING.md)
Lien relatif vers une section d'un autre fichier : [API](docs/api.md#authentification)

[Lien par référence][doc-github]

[doc-github]: https://docs.github.com
````

**Rendu :** des liens cliquables. Le dernier exemple définit l'URL une fois en bas de document, pratique quand elle revient souvent.

**Comment est calculée l'ancre d'un titre :** GitHub met le titre en minuscules, remplace les espaces par des tirets et supprime la ponctuation. Si deux titres sont identiques, le second reçoit le suffixe `-1`, le troisième `-2`, etc.

| Titre | Ancre |
| --- | --- |
| `## Installation` | `#installation` |
| `## Démarrage rapide` | `#démarrage-rapide` |
| `## Qu'est-ce que c'est ?` | `#quest-ce-que-cest-` |
| `## API (v2)` | `#api-v2` |
| `## C++ & Rust` | `#c--rust` |

**Erreurs fréquentes :**

- Lien interne vers une ancre qui n'existe plus après un renommage de titre : vérifie les liens à chaque modification (voir [G.12](#g12-vérification-des-liens-et-des-images)).
- Texte de lien `cliquez ici` : écris un texte qui a du sens hors contexte (`consulter le guide d'installation`).
- Lien absolu vers sa propre branche (`https://github.com/OWNER/REPO/blob/main/...`) : préfère un lien relatif, qui suit la branche consultée.
- Texte de lien réparti sur plusieurs lignes : à éviter pour les liens relatifs.

### B.7 Images et GIF

**Utilité :** montrer le projet (capture d'écran, schéma, démo animée).

````markdown
![Capture d'écran du tableau de bord](docs/assets/dashboard.png)
![Démo en GIF animé](docs/assets/demo.gif)
[![Cliquer pour agrandir](docs/assets/thumb.png)](docs/assets/full.png)
````

La syntaxe est `![texte alternatif](chemin-ou-url)`. Le **texte alternatif** décrit l'image pour les lecteurs d'écran et s'affiche si l'image ne charge pas. La troisième ligne est une image cliquable : une image placée dans la syntaxe d'un lien.

**Rendu :** l'image est affichée à sa taille naturelle, plafonnée à la largeur de la page. Pour contrôler les dimensions, utilise une balise HTML (voir [D.5](#d5-alignement-et-dimensions-des-images)).

**Erreurs fréquentes :**

- Texte alternatif vide ou `image` : décris le contenu utile.
- Chemin relatif faux (casse, dossier) : sous Linux/GitHub, `Docs/Demo.png` et `docs/demo.png` sont deux fichiers différents.
- GIF de 40 Mo : lent à charger, difficile à relire. Voir [D.4](#d4-captures-décran-et-gif-de-démonstration).
- Image locale non commitée : elle s'affiche chez toi, pas sur GitHub.

### B.8 Séparateurs

**Utilité :** marquer une rupture thématique (rarement nécessaire : un titre fait souvent mieux).

````markdown
Texte avant.

---

Texte après.
````

**Rendu :** un trait horizontal fin.

---

**Erreurs fréquentes :** placer `---` **directement sous une ligne de texte**, sans ligne vide : le texte devient alors un titre de niveau 2. Laisse toujours une ligne vide avant.

### B.9 Code inline

**Utilité :** signaler un nom de fichier, une commande courte, une variable, une valeur.

````markdown
Lance `npm install` puis ouvre le fichier `.env`.
Pour afficher un backtick, double les délimiteurs : `` `code` ``.
````

**Rendu :** Lance `npm install` puis ouvre le fichier `.env`. Pour afficher un backtick, double les délimiteurs : `` `code` ``.

La suite est détaillée en [section C](#c-les-blocs-de-code).

### B.10 Blocs de code

**Utilité :** afficher plusieurs lignes de code ou de commandes, avec indentation préservée et bouton « Copier ».

`````markdown
```
npm install
npm run build
```
`````

Le bloc se délimite avec trois backticks (ou trois tildes `~~~`) avant et après. Voir [section C](#c-les-blocs-de-code) pour la coloration, les langages et les pièges.

### B.11 Blocs de code avec indication du langage

**Utilité :** activer la coloration syntaxique en ajoutant l'identifiant du langage juste après les backticks ouvrants.

`````markdown
```python
def hello(name: str) -> str:
    return f"Hello, {name}!"
```
`````

**Rendu :**

```python
def hello(name: str) -> str:
    return f"Hello, {name}!"
```

Le catalogue des identifiants est en [C.3](#c3-choisir-le-bon-identifiant-de-langage).

### B.12 Tableaux

**Utilité :** comparer des éléments selon plusieurs critères (options, versions, commandes).

````markdown
| Commande       | Description              | Défaut |
| :------------- | :----------------------: | -----: |
| `npm start`    | Lance le serveur         | 3000   |
| `npm test`     | Lance les tests          | —      |
| `npm run lint` | Vérifie le style du code | —      |
````

**Rendu :**

| Commande       | Description              | Défaut |
| :------------- | :----------------------: | -----: |
| `npm start`    | Lance le serveur         | 3000   |
| `npm test`     | Lance les tests          | —      |
| `npm run lint` | Vérifie le style du code | —      |

Les deux-points de la ligne de séparation règlent l'alignement : `:---` à gauche, `:---:` centré, `---:` à droite. Il n'est pas nécessaire d'aligner les `|` dans le source, c'est seulement plus lisible.

**Erreurs fréquentes :**

- Oublier la ligne de séparation `| --- | --- |` : le tableau n'est pas reconnu.
- Nombre de colonnes différent d'une ligne à l'autre.
- Une barre verticale `|` dans une cellule : écris `\|`.
- Vouloir des cellules fusionnées ou des listes dans les cellules : impossible en Markdown (voir [G.4](#g4-tableaux-complexes-et-limitations)).

### B.13 Cases à cocher

**Utilité :** listes de tâches, roadmap, checklists.

````markdown
- [x] Fonctionnalité terminée
- [ ] Fonctionnalité à faire
- [ ] Autre tâche
````

**Rendu :**

- [x] Fonctionnalité terminée
- [ ] Fonctionnalité à faire
- [ ] Autre tâche

Dans un fichier README, les cases sont **en lecture seule** : pour les cocher, il faut modifier le fichier. Elles sont interactives dans les issues et les pull requests.

**Erreurs fréquentes :** oublier l'espace dans `[ ]`, ou écrire `[X ]`. Le format est `- [ ]` ou `- [x]`, avec l'espace après le tiret.

### B.14 Échappement des caractères Markdown

**Utilité :** afficher littéralement un caractère qui a un sens en Markdown (`*`, `_`, `#`, `` ` ``, `[`, `|`, `<`…).

````markdown
\*pas en italique\*
\# pas un titre
1\. pas une liste numérotée
Prix : 5 \| 10 euros
\<balise\> affichée telle quelle
````

**Rendu :**

\*pas en italique\*
\# pas un titre
1\. pas une liste numérotée
Prix : 5 \| 10 euros
\<balise\> affichée telle quelle

Caractères échappables avec `\` : `` \ ` * _ { } [ ] ( ) # + - . ! | ``. Dans du **code** (inline ou bloc), il ne faut pas échapper : tout est affiché tel quel.

**Erreurs fréquentes :** échapper à l'intérieur d'un bloc de code (la barre oblique s'affiche), ou oublier d'échapper un `<` : GitHub peut le traiter comme du HTML et faire disparaître le texte.

### B.15 HTML compatible avec GitHub

**Utilité :** obtenir ce que Markdown ne sait pas faire : centrer, redimensionner, replier, afficher des touches.

````markdown
<div align="center">
  <h1>Mon projet</h1>
  <p><em>Une phrase d'accroche.</em></p>
</div>

<img src="docs/assets/logo.png" alt="Logo du projet" width="120">

Appuie sur <kbd>Ctrl</kbd> + <kbd>C</kbd>.

<details>
<summary>Cliquer pour voir les détails</summary>

Contenu masqué par défaut. Le Markdown fonctionne ici, **à condition de laisser une ligne vide**
après la balise `<summary>`.

</details>

<!-- Ce commentaire est invisible dans le rendu. -->
````

**Rendu :**

<div align="center">
  <em>Texte centré avec le HTML.</em>
</div>

Appuie sur <kbd>Ctrl</kbd> + <kbd>C</kbd>.

<details>
<summary>Cliquer pour voir les détails</summary>

Contenu masqué par défaut. Le Markdown fonctionne ici, **à condition de laisser une ligne vide** après la balise `<summary>`.

</details>

<!-- Ce commentaire est invisible dans le rendu. -->

**Ce que GitHub accepte et refuse.** GitHub **filtre** le HTML (assainissement) :

| Autorisé (en général) | Retiré ou ignoré |
| --- | --- |
| `div`, `p`, `span`, `br`, `hr`, `h1`–`h6` | `script`, `iframe`, `object`, `embed` |
| `img`, `picture`, `source`, `a` | `style` et l'attribut `style` |
| `table`, `thead`, `tr`, `th`, `td` | l'attribut `class`, les événements (`onclick`…) |
| `details`, `summary`, `kbd`, `sub`, `sup`, `ins`, `del` | `form`, `input`, `button` |
| attributs `align`, `width`, `height`, `alt`, `src`, `href` | polices et CSS personnalisés |

Cette liste décrit le comportement observé et peut évoluer : teste toujours dans l'aperçu avant de t'appuyer sur un détail HTML.

**Erreurs fréquentes :**

- Compter sur `style="..."` pour la couleur ou l'espacement : ignoré sur GitHub.
- Oublier de fermer une balise : tout ce qui suit peut être absorbé.
- Écrire du Markdown dans un bloc HTML sans ligne vide autour : il n'est pas interprété.

### B.16 Syntaxes GitHub Flavored Markdown (GFM)

Ce que GFM ajoute à Markdown « classique » :

| Fonction | Syntaxe | Remarque |
| --- | --- | --- |
| Tableaux | `\| a \| b \|` | voir [B.12](#b12-tableaux) |
| Cases à cocher | `- [ ]` | voir [B.13](#b13-cases-à-cocher) |
| Barré | `~~texte~~` | voir [B.2](#b2-gras-italique-barré) |
| Liens automatiques | `https://exemple.org` | une URL nue devient un lien |
| Mentions | `@utilisateur`, `@org/équipe` | notifient la personne ; à utiliser dans issues et PR plutôt que dans un README |
| Références | `#123` | lien vers l'issue ou la PR 123 du dépôt |
| Emoji | `:tada:` | voir [D.9](#d9-emojis) |
| Notes de bas de page | `texte[^1]` puis `[^1]: Note.` | rendues en fin de document |
| Alertes | `> [!NOTE]` | voir [B.17](#b17-notes-alertes-et-avertissements-github) |
| Diagrammes | bloc ```` ```mermaid ```` | flowchart, séquence, Gantt… rendus nativement |
| Formules | `$E=mc^2$` ou `$$ … $$` | rendues avec MathJax |

Exemple de **diagramme Mermaid**, très utile pour une section « Architecture » :

`````markdown
```mermaid
flowchart LR
    Client --> API --> DB[(Base de données)]
```
`````

**Rendu :**

```mermaid
flowchart LR
    Client --> API --> DB[(Base de données)]
```

### B.17 Notes, alertes et avertissements GitHub

**Utilité :** attirer l'attention sur une information précise, avec une icône et une couleur.

````markdown
> [!NOTE]
> Information utile, même en lecture rapide.

> [!TIP]
> Conseil pour faire mieux ou plus simple.

> [!IMPORTANT]
> Information essentielle pour réussir.

> [!WARNING]
> Risque ou comportement qui demande de l'attention.

> [!CAUTION]
> Danger : perte de données, problème de sécurité.
````

**Rendu :**

> [!NOTE]
> Information utile, même en lecture rapide.

> [!TIP]
> Conseil pour faire mieux ou plus simple.

> [!IMPORTANT]
> Information essentielle pour réussir.

> [!WARNING]
> Risque ou comportement qui demande de l'attention.

> [!CAUTION]
> Danger : perte de données, problème de sécurité.

**Quand utiliser quoi :**

| Type | Usage typique dans un README |
| --- | --- |
| `NOTE` | Précision : « fonctionne aussi sous Windows via WSL » |
| `TIP` | Astuce : « active le mode watch pour recharger automatiquement » |
| `IMPORTANT` | Prérequis bloquant : « Node.js 20 minimum » |
| `WARNING` | « Cette commande écrase la base locale » |
| `CAUTION` | « N'expose jamais cette clé publiquement » |

**Bonnes pratiques :** limite-toi à une ou deux alertes par document, ne les imbrique pas, et ne remplace pas tout un paragraphe par une alerte. Écris le marqueur `[!TYPE]` en majuscules, seul sur sa ligne : le texte commence à la ligne suivante.

**Erreurs fréquentes :** écrire `> [!NOTE] texte` sur la même ligne que le marqueur, ou utiliser une alerte sur un autre site qui ne supporte pas la syntaxe (npm, PyPI, générateurs de documentation : elle s'y affiche comme une simple citation).

### B.18 Autres éléments utiles

**Mentions de compatibilité.** Certains éléments ne s'affichent que sur GitHub (alertes, Mermaid, mentions). Si ton README est aussi publié sur npm, PyPI ou un site de documentation, vérifie le rendu sur chaque plateforme.

**Commentaires cachés** pour les marqueurs d'automatisation (par exemple, une zone générée) : `<!-- BEGIN GENERATED -->`.

**Notes de bas de page :**

````markdown
Le format est inspiré de la spécification Standard Readme[^1].

[^1]: Spécification disponible dans le dépôt `RichardLitt/standard-readme`.
````

---

## C. Les blocs de code

Le code est le contenu le plus important de la plupart des README : c'est ce que le lecteur copie, exécute et vérifie. Soigne-le.

### C.1 Code inline ou bloc de code

| | Code inline | Bloc de code |
| --- | --- | --- |
| **Délimiteurs** | un backtick de chaque côté | trois backticks (ou `~~~`) sur leur propre ligne |
| **Usage** | un mot, un nom de fichier, une option, une variable | une commande complète, plusieurs lignes, une config |
| **Coloration** | aucune | oui, si le langage est indiqué |
| **Bouton « Copier »** | non | oui |
| **Indentation conservée** | non | oui |

Règle simple : **si le lecteur doit le copier, utilise un bloc. S'il doit seulement le reconnaître dans une phrase, utilise du code inline.**

````markdown
Le fichier `config.yml` contient l'option `debug`.

```bash
npm install --save-dev prettier
```
````

### C.2 Pourquoi préciser le langage

- **Lisibilité :** la coloration syntaxique distingue mots-clés, chaînes et commentaires.
- **Détection d'erreurs :** une faute de syntaxe (guillemet oublié) se voit tout de suite.
- **Cohérence :** tous les extraits ont la même allure.
- **Accessibilité et outils :** certains outils (recherche, linters de Markdown) exploitent l'identifiant.

Sans identifiant, le bloc s'affiche en texte brut, sans couleur. GitHub peut parfois deviner le langage, mais ne t'y fie pas. Le lintage Markdown (règle `MD040` de markdownlint) signale les blocs sans langage (voir [G.13](#g13-automatisation-des-contrôles)).

### C.3 Choisir le bon identifiant de langage

GitHub s'appuie sur la bibliothèque **Linguist** : l'identifiant est le nom du langage (insensible à la casse) ou un alias. En cas de doute, regarde la liste des langages de Linguist (fichier `languages.yml`) ou teste dans l'aperçu : si la coloration apparaît, c'est bon. Un identifiant inconnu ne provoque pas d'erreur, le bloc reste simplement sans couleur.

| Contenu | Identifiant conseillé | Alias courants |
| --- | --- | --- |
| Python | `python` | `py` |
| JavaScript | `javascript` | `js` |
| TypeScript | `typescript` | `ts` |
| JSX / TSX | `jsx` / `tsx` | |
| HTML | `html` | |
| CSS / SCSS | `css` / `scss` | |
| JSON | `json` | `jsonc` pour JSON avec commentaires |
| Shell Unix (commandes) | `bash` | `sh`, `shell`, `zsh` |
| Session de terminal avec sortie | `console` | `shell-session` |
| PowerShell | `powershell` | `ps1`, `pwsh` |
| Invite de commandes Windows | `batch` | `bat`, `cmd` |
| SQL | `sql` | |
| YAML | `yaml` | `yml` |
| TOML | `toml` | |
| INI / `.env` | `ini` / `dotenv` | `env` |
| Dockerfile | `dockerfile` | `docker` |
| XML | `xml` | |
| Markdown | `markdown` | `md` |
| Différences (diff) | `diff` | |
| C / C++ / C# | `c` / `cpp` / `csharp` | `cs` |
| Java / Kotlin / Swift | `java` / `kotlin` / `swift` | |
| Go / Rust | `go` / `rust` | `rs` |
| PHP / Ruby | `php` / `ruby` | `rb` |
| Makefile | `makefile` | `make` |
| GraphQL | `graphql` | |
| Diagramme Mermaid | `mermaid` | rendu en schéma |
| Texte brut | `text` | `plaintext`, `txt` |

### C.4 Exemples par langage

Chaque exemple montre le **Markdown à écrire** (bloc externe de quatre backticks). Le rendu est le bloc intérieur, coloré selon le langage.

**Python et JavaScript**

````markdown
```python
from pathlib import Path

def read_lines(path: str) -> list[str]:
    """Retourne les lignes non vides d'un fichier."""
    return [l for l in Path(path).read_text().splitlines() if l.strip()]
```

```javascript
// Retourne la somme d'un tableau de nombres
const sum = (values) => values.reduce((a, b) => a + b, 0);
console.log(sum([1, 2, 3])); // 6
```
````

**Rendu :**

```python
from pathlib import Path

def read_lines(path: str) -> list[str]:
    """Retourne les lignes non vides d'un fichier."""
    return [l for l in Path(path).read_text().splitlines() if l.strip()]
```

```javascript
// Retourne la somme d'un tableau de nombres
const sum = (values) => values.reduce((a, b) => a + b, 0);
console.log(sum([1, 2, 3])); // 6
```

**TypeScript, HTML et CSS**

````markdown
```typescript
interface User {
  id: number;
  name: string;
}

export function greet(user: User): string {
  return `Bonjour ${user.name}`;
}
```

```html
<button class="btn" type="button">Envoyer</button>
```

```css
.btn {
  padding: 0.5rem 1rem;
  border-radius: 4px;
}
```
````

**JSON et YAML**

````markdown
```json
{
  "name": "mon-projet",
  "version": "1.0.0",
  "scripts": { "start": "node index.js" }
}
```

```yaml
services:
  web:
    image: nginx:1.27
    ports:
      - "8080:80"
```
````

> [!NOTE]
> Le JSON n'accepte pas les commentaires. Si ton extrait en contient, utilise l'identifiant `jsonc`, sinon la coloration signalera des erreurs.

**Bash, PowerShell et SQL**

````markdown
```bash
git clone https://github.com/OWNER/REPO.git
cd REPO
./scripts/setup.sh
```

```powershell
git clone https://github.com/OWNER/REPO.git
Set-Location REPO
.\scripts\setup.ps1
```

```sql
SELECT id, email
FROM users
WHERE created_at >= '2026-01-01'
ORDER BY created_at DESC
LIMIT 10;
```
````

**Dockerfile, Go, Rust**

````markdown
```dockerfile
FROM node:22-alpine
WORKDIR /app
COPY package*.json ./
RUN npm ci --omit=dev
COPY . .
CMD ["node", "server.js"]
```

```go
package main

import "fmt"

func main() { fmt.Println("Bonjour") }
```

```rust
fn main() {
    println!("Bonjour");
}
```
````

### C.5 Commandes de terminal lisibles

Principes pour des commandes **copiables** :

1. **Pas de `$` devant les commandes** dans un bloc `bash` : le bouton « Copier » copierait aussi le `$`.
2. **Une action par commande**, commentée si ce n'est pas évident.
3. **Sépare la commande de sa sortie** : la commande dans un bloc `bash`, la sortie dans un bloc `text`. Si tu dois montrer une session entière, utilise `console` avec `$` devant les commandes.
4. **Adapte aux systèmes** : donne les variantes Windows (PowerShell) et Unix quand elles diffèrent.
5. **Remplace** les valeurs sensibles ou personnelles par des placeholders (voir [G.10](#g10-prévention-des-informations-sensibles-dans-les-exemples)).

````markdown
Installe puis lance le projet :

```bash
# Installe les dépendances
npm install

# Démarre le serveur de développement (http://localhost:3000)
npm run dev
```

Résultat attendu :

```text
> Server ready on http://localhost:3000
```

Session de terminal complète (commandes précédées de `$`) :

```console
$ node --version
v22.11.0
```
````

**Rendu :**

Installe puis lance le projet :

```bash
# Installe les dépendances
npm install

# Démarre le serveur de développement (http://localhost:3000)
npm run dev
```

Résultat attendu :

```text
> Server ready on http://localhost:3000
```

Session de terminal complète (commandes précédées de `$`) :

```console
$ node --version
v22.11.0
```

**Plusieurs systèmes :** pour éviter un long README, plie les variantes dans `<details>` :

`````markdown
<details>
<summary>Windows (PowerShell)</summary>

```powershell
py -m venv .venv
.\.venv\Scripts\Activate.ps1
```

</details>
`````

### C.6 Extraits de configuration

Un extrait de configuration doit répondre à : **dans quel fichier ? quelle partie ? quoi changer ?**

- Annonce le **nom du fichier** avant le bloc.
- Montre seulement les lignes utiles et signale les coupures avec un commentaire (`# ...`).
- Utilise un bloc `diff` pour montrer une modification.
- Précise ce qui est **à remplacer**.

`````markdown
Dans `.env`, copie le modèle puis renseigne tes valeurs :

```dotenv
DATABASE_URL=postgres://USER:PASSWORD@localhost:5432/mydb
API_KEY=YOUR_API_KEY_HERE
```

Dans `package.json`, ajoute le script suivant :

```diff
 "scripts": {
   "start": "node index.js",
+  "lint": "eslint ."
 }
```
`````

**Rendu :**

Dans `.env`, copie le modèle puis renseigne tes valeurs :

```dotenv
DATABASE_URL=postgres://USER:PASSWORD@localhost:5432/mydb
API_KEY=YOUR_API_KEY_HERE
```

Dans `package.json`, ajoute le script suivant :

```diff
 "scripts": {
   "start": "node index.js",
+  "lint": "eslint ."
 }
```

### C.7 Mauvais bloc, bon bloc

**Mauvais :** pas de langage, prompt copié, pas de contexte, secret réel, commandes enchaînées sans explication.

````markdown
```
$ cd mon-projet && npm i && cp .env.example .env && nano .env
API_KEY=sk_live_51Hxxxxxxxxxxxxxxxxxxx
$ npm start
```
````

**Bon :** langage indiqué, une étape par bloc, placeholder, commentaire.

`````markdown
1. Installe les dépendances :

   ```bash
   npm install
   ```

2. Crée ton fichier d'environnement et renseigne ta clé :

   ```bash
   cp .env.example .env
   ```

   ```dotenv
   API_KEY=YOUR_API_KEY_HERE
   ```

3. Lance l'application :

   ```bash
   npm start
   ```
`````

| Défaut du mauvais bloc | Correction dans le bon bloc |
| --- | --- |
| Pas de langage | `bash`, `dotenv` |
| `$` copié avec la commande | Commandes sans prompt |
| Trop de choses sur une ligne | Une étape, un bloc |
| Clé qui ressemble à une vraie | Placeholder explicite `YOUR_API_KEY_HERE` |
| Pas de contexte | Texte avant chaque bloc |

### C.8 Erreurs de délimitation et backticks imbriqués

**Le principe :** un bloc de code se ferme dès qu'une ligne contient **au moins autant de backticks** que l'ouverture (même caractère). Pour afficher un bloc de trois backticks **dans** un autre bloc, il faut donc que le bloc externe soit **plus long** : quatre backticks pour contenir trois, cinq pour contenir quatre, etc.

C'est exactement ce que fait ce guide. Le bloc ci-dessous est lui-même écrit avec **neuf** backticks pour pouvoir afficher un bloc à **cinq** backticks, qui contient un bloc à quatre, qui contient un bloc à trois :

`````````markdown
`````markdown
````markdown
```bash
echo "bloc le plus intérieur"
```
````
`````
`````````

Vue d'ensemble des cas :

| Besoin | Délimiteur externe | Exemple de contenu |
| --- | --- | --- |
| Code simple | 3 backticks | du code |
| Montrer un bloc de code | 4 backticks | un bloc à 3 backticks |
| Montrer un bloc qui en contient un autre | 5 backticks | un bloc à 4 backticks |
| Alternative | `~~~` (tildes) | un bloc à backticks, sans compter |

**Alternative avec les tildes :** l'externe en `~~~` et l'interne en backticks ne se gênent pas.

`````markdown
~~~markdown
```bash
echo "bonjour"
```
~~~
`````

**Backtick dans du code inline :** utilise des délimiteurs plus longs que la séquence interne, avec une espace de chaque côté.

````markdown
Écris `` ` `` pour un backtick, et ``` `` ``` pour deux.
````

**Les erreurs classiques :**

| Erreur | Symptôme | Correction |
| --- | --- | --- |
| Bloc non fermé | Tout le reste du README s'affiche en code | Ajoute la fermeture |
| Fermeture plus courte que l'ouverture | Le bloc ne se ferme pas | Même nombre (ou plus) de backticks |
| Backticks internes de même longueur que les externes | Le bloc se coupe au milieu | Rallonge l'externe ou passe aux tildes |
| Espace avant les backticks hors liste | Indenté de 4 espaces, le bloc devient un « code indenté » | Aligne à la marge, 0 à 3 espaces |
| Bloc dans une liste non indenté | La liste est interrompue | Indente comme le texte de l'élément |
| Caractères typographiques (guillemets « intelligents ») collés d'un traitement de texte | Code qui ne s'exécute pas | Écris dans un éditeur de code |
| Faute de frappe dans l'identifiant (`pyhton`) | Pas de coloration, sans message d'erreur | Vérifie l'identifiant dans le tableau [C.3](#c3-choisir-le-bon-identifiant-de-langage) |

---

## D. Les éléments visuels

Les éléments visuels servent à **informer plus vite**, pas à décorer. Chacun doit répondre à une question que le lecteur se pose.

### D.1 Badges

**Utilité :** afficher en un coup d'œil l'état du projet : build qui passe, version publiée, licence, couverture de tests, nombre d'étoiles.

**Création.** Un badge est une image. Deux sources courantes :

1. **Badge natif GitHub Actions**, sans service tiers :

   ````markdown
   [![CI](https://github.com/OWNER/REPO/actions/workflows/ci.yml/badge.svg)](https://github.com/OWNER/REPO/actions/workflows/ci.yml)
   ````

2. **[Shields.io](https://shields.io)**, pour la licence, la version, les étoiles, etc. (service tiers : l'URL exacte et les routes disponibles peuvent évoluer, vérifie sur le site) :

   ````markdown
   [![Licence](https://img.shields.io/github/license/OWNER/REPO)](LICENSE)
   [![Version npm](https://img.shields.io/npm/v/PACKAGE)](https://www.npmjs.com/package/PACKAGE)
   [![Étoiles](https://img.shields.io/github/stars/OWNER/REPO?style=social)](https://github.com/OWNER/REPO/stargazers)
   ![Badge statique](https://img.shields.io/badge/Node-%E2%89%A5%2020-339933)
   ````

La syntaxe est une **image dans un lien** : `[![texte alternatif](url-du-badge)](url-de-destination)`. Dans un badge statique `badge/<label>-<message>-<couleur>`, les espaces s'écrivent `%20` ou `_`, et un tiret littéral se double : `--`.

**Bonnes pratiques :**

| À faire | À éviter |
| --- | --- |
| 3 à 6 badges, **utiles** | 15 badges décoratifs |
| Sur une ou deux lignes, juste sous le titre | Badges éparpillés dans le texte |
| Un texte alternatif parlant | Texte alternatif vide |
| Des badges **dynamiques** (état réel) | Un « build passing » écrit à la main |
| Un lien qui mène à la source du statut | Badge non cliquable |
| Un style homogène (`flat`, `for-the-badge`…) | Mélange de styles |

Badges pertinents selon le projet : **build/CI**, **version publiée**, **licence**, **couverture de tests**, **version minimale du runtime**. Inutiles pour la plupart : « made with ❤️ », « PRs welcome » (dis-le dans la section contribution), nombre de commits.

### D.2 Logos et bannières

**Utilité :** donner une identité visuelle et reconnaître le projet dès le coup d'œil.

- **Logo :** carré ou horizontal, **format SVG** de préférence (net à toutes les tailles), 100 à 200 px de large dans le README.
- **Bannière :** image large (par exemple 1280 × 320 px), sobre, avec le nom du projet **aussi écrit en texte** dans le README (une image de texte n'est pas lisible par un lecteur d'écran ni indexable).
- **Image de partage social :** dans les réglages du dépôt, tu peux envoyer une image (recommandée : 1280 × 640 px) qui s'affiche quand le lien est partagé sur les réseaux sociaux.
- **Version claire et sombre :** prévois les deux, voir [D.12](#d12-compatibilité-avec-le-thème-sombre-et-clair).

`````markdown
<p align="center">
  <img src="docs/assets/logo.svg" alt="Logo de MonProjet" width="140">
</p>

<h1 align="center">MonProjet</h1>

<p align="center">Une phrase qui dit ce que fait le projet.</p>
`````

### D.3 Aperçu visuel dans le README

Un aperçu (capture, GIF, schéma) se place **après la présentation courte** et **avant l'installation** : le lecteur voit ce qu'il va obtenir avant de décider de continuer. Choisis le support selon ce que tu montres :

| Tu veux montrer… | Support conseillé |
| --- | --- |
| Une interface fixe | Capture d'écran PNG |
| Un parcours ou une animation | GIF court (5 à 15 s) ou vidéo |
| Un outil en ligne de commande | GIF de terminal (voir [D.4](#d4-captures-décran-et-gif-de-démonstration)) |
| Une architecture | Diagramme Mermaid ou SVG |
| Un avant / après | Deux captures côte à côte (tableau HTML) |

### D.4 Captures d'écran et GIF de démonstration

**Captures d'écran :**

- Format **PNG** pour les interfaces, **JPEG/WebP** pour les photos.
- Largeur utile entre 800 et 1 600 px, poids raisonnable (idéalement quelques centaines de Ko).
- Recadre sur l'essentiel, **masque les données personnelles** (e-mails, jetons, noms).
- Une capture par message, avec une légende.

**GIF de démonstration :**

- Court, au point : une seule fonctionnalité, 5 à 15 secondes.
- Poids maîtrisé : vise **quelques Mo** au maximum, sinon le chargement est lent (surtout sur mobile).
- Pas de texte trop petit, pas de défilement rapide.
- Outils courants : **vhs** (Charmbracelet, pour scripter un GIF de terminal reproductible), **Gifski** (compression de qualité), **ScreenToGif** (Windows, éditeur intégré), **LICEcap**.
- Pour les démos longues, préfère une **vidéo** hébergée ailleurs et une image cliquable qui y mène.

`````markdown
<p align="center">
  <img src="docs/assets/demo.gif" alt="Démonstration : création d'un projet en trois commandes" width="720">
</p>
`````

### D.5 Alignement et dimensions des images

Markdown ne sait ni aligner ni redimensionner. Utilise HTML :

````markdown
<!-- Largeur fixe, hauteur proportionnelle -->
<img src="docs/assets/screenshot.png" alt="Écran d'accueil" width="600">

<!-- Centrée -->
<p align="center"><img src="docs/assets/screenshot.png" alt="Écran d'accueil" width="600"></p>

<!-- Deux images côte à côte -->
<p align="center">
  <img src="docs/assets/light.png" alt="Thème clair" width="45%">
  <img src="docs/assets/dark.png"  alt="Thème sombre" width="45%">
</p>
````

**Bonnes pratiques :** indique `width` plutôt que `height` (le ratio est conservé), préfère les pourcentages pour la fluidité sur mobile, et ne dépasse pas la largeur du contenu (environ 900 px sur ordinateur).

### D.6 Images hébergées et chemins relatifs

| Méthode | Exemple | Avantages | Inconvénients |
| --- | --- | --- | --- |
| **Chemin relatif** | `docs/assets/logo.png` | Versionné avec le code, suit la branche, fonctionne hors ligne | S'affiche mal sur npm/PyPI/autres sites |
| **URL « raw » absolue** | `https://raw.githubusercontent.com/OWNER/REPO/main/docs/assets/logo.png` | Fonctionne partout | Longue, dépend du nom de la branche |
| **Image envoyée via une issue ou une PR** | URL `user-images` / `user-attachments` | Pas de fichier dans le dépôt | Hors versionnage, difficile à maintenir |
| **Service externe** | URL d'un tiers | Aucun | Peut disparaître, fuite d'adresse IP vers un tiers |

**Recommandation :** images dans le dépôt (`docs/assets/` ou `.github/assets/`), chemins relatifs. Si le README est republié sur npm ou PyPI, utilise des URL absolues pour les images de ce README-là.

GitHub passe par un proxy d'images : quand tu remplaces une image, il peut falloir un peu de temps (cache) avant de voir la nouvelle version. Si besoin, change le nom du fichier.

### D.7 Tableaux de bord de statistiques GitHub

Des services tiers génèrent des cartes (langages principaux, statistiques de contribution, séries d'activité) que l'on insère dans un README de profil.

`````markdown
<!-- Exemple générique : adapte l'URL au service que tu choisis -->
![Statistiques GitHub de OWNER](https://github-readme-stats.example/api?username=OWNER&show_icons=true)
`````

> [!WARNING]
> Ces cartes dépendent de **services tiers** : elles peuvent être lentes, limitées en nombre de requêtes, indisponibles, ou changer de paramètres. Vérifie la documentation du service au moment de l'intégrer. Le domaine `github-readme-stats.example` ci-dessus est un **placeholder** à remplacer.

**Bonnes pratiques :**

- Une ou deux cartes suffisent : trop de statistiques noie le message.
- Prévois un **texte alternatif** explicite, et ne mets pas d'information essentielle uniquement dans la carte.
- Un chiffre (étoiles, commits) ne démontre pas la qualité d'un travail : mets plutôt en avant tes projets.
- Pour la fiabilité, tu peux héberger toi-même le service ou générer l'image via GitHub Actions et la commiter.

### D.8 Séparateurs et mise en page

- **Titres** avant tout séparateur : un `##` structure mieux qu'un trait.
- `---` : pause forte entre grandes parties (peu souvent).
- `<details>` : replie le contenu secondaire (variantes d'OS, logs, FAQ longue).
- **Tableaux** pour comparer, **listes** pour énumérer, **paragraphes courts** (3 à 4 lignes) pour expliquer.
- Garde une **largeur de code raisonnable** (moins de 80 à 100 caractères par ligne) pour éviter le défilement horizontal.

````markdown
<details>
<summary><strong>Dépannage : erreur EADDRINUSE</strong></summary>

Le port 3000 est déjà utilisé. Change-le avec `PORT=3001 npm start`.

</details>
````

### D.9 Emojis

| Bon usage | Mauvais usage |
| --- | --- |
| Repère visuel discret et **cohérent** dans les titres de section ou les listes de fonctionnalités | Un emoji devant chaque ligne |
| Marquer l'état (✅ / ❌) dans un tableau de compatibilité | Remplacer des mots essentiels |
| Ton léger pour un projet personnel | Documentation sérieuse ou institutionnelle |

**Attention :**

- Les emojis dans les **titres** compliquent les ancres de liens internes : copie l'URL d'ancre depuis GitHub et teste le lien.
- Les lecteurs d'écran lisent chaque emoji à voix haute (« boîte à outils », « fusée »…) : n'en mets pas dix à la suite.
- L'affichage varie selon les systèmes.
- Tu peux les écrire en caractère Unicode ou en code court `:rocket:`.

**Règle simple :** si tu enlèves tous les emojis et que le README reste clair, tu les utilises bien.

### D.10 Accessibilité

- **Texte alternatif** pour chaque image porteuse de sens ; `alt=""` pour une image purement décorative.
- **Ne mets pas de texte important dans une image** (bannière, schéma) sans le répéter dans le texte.
- **Hiérarchie de titres** sans saut de niveau.
- **Liens explicites** : « guide d'installation » plutôt que « ici ».
- **Contraste et couleur :** ne transmets pas une information uniquement par la couleur (✅/❌ plutôt que vert/rouge seul).
- **Tableaux simples** avec une ligne d'en-tête.
- **Vidéos et GIF :** décris ce qu'ils montrent en une phrase.
- **Emojis et ASCII art :** en petite quantité (les lecteurs d'écran les épellent).

### D.11 Affichage sur mobile

L'application GitHub et le site mobile ont une largeur d'environ 360 à 420 px.

- **Tableaux larges :** limite à 3 ou 4 colonnes, ou remplace par une liste.
- **Lignes de code longues :** coupe-les avec `\` en shell, ou raccourcis.
- **Images :** `width="100%"` ou largeur en pourcentage plutôt que 1 200 px fixes.
- **Badges :** une ligne qui revient à la ligne est acceptable ; 15 badges ne le sont pas.
- **Éléments côte à côte** : à tester sur petit écran (ils passent en colonne ou débordent).
- Teste avec l'outil de simulation d'appareil de ton navigateur.

### D.12 Compatibilité avec le thème sombre et clair

GitHub propose un thème clair et un thème sombre, et chaque lecteur choisit le sien. Une image à fond blanc ou un logo noir peuvent devenir illisibles.

**Méthode recommandée : l'élément `<picture>`**, qui sert une image selon le thème :

````markdown
<picture>
  <source media="(prefers-color-scheme: dark)" srcset="docs/assets/logo-dark.svg">
  <source media="(prefers-color-scheme: light)" srcset="docs/assets/logo-light.svg">
  <img alt="Logo de MonProjet" src="docs/assets/logo-light.svg" width="160">
</picture>
````

L'`<img>` interne sert de repli. Une ancienne méthode consistait à ajouter `#gh-dark-mode-only` ou `#gh-light-mode-only` à la fin de l'URL de l'image ; elle existe encore dans de nombreux dépôts, mais `<picture>` est la méthode à privilégier.

**Autres astuces :**

- Choisis des logos avec **fond transparent** et des couleurs lisibles sur les deux thèmes.
- Une capture d'écran avec une fine bordure reste lisible sur les deux fonds.
- Préfère les badges qui adaptent leur couleur automatiquement (Shields.io en standard).
- Teste dans **les deux thèmes** (Réglages GitHub → Apparence).

### D.13 Les limites de GitHub

| Limite | Détail |
| --- | --- |
| **HTML filtré** | Pas de `script`, `iframe`, `style`, attribut `class` : pas de mise en page libre |
| **Pas de CSS ni de JavaScript** | Aucun style personnalisé, aucune interactivité (sauf `<details>`) |
| **Pas de police personnalisée** | Police de GitHub imposée |
| **Taille du README** | Contenu tronqué au-delà de 500 KiB |
| **Images** | Proxy avec cache ; un SVG s'affiche comme image, sans script ni ressource externe |
| **Vidéos** | Support variable selon le contexte : teste avant de t'y fier, et prévois un lien de repli |
| **Services tiers** | Badges et cartes dépendent de leur disponibilité |
| **Rendu différent ailleurs** | npm, PyPI, Docker Hub, VS Code Marketplace et sites de docs ont chacun leur moteur Markdown |
| **Pas de mise en page responsive avancée** | Pas de grilles ni de colonnes réelles ; les tableaux HTML sont le seul contournement |

**Principe :** garde un README **robuste**. Si une personnalisation disparaissait demain, le README doit rester lisible et complet.

---

## E. Structure d'un README professionnel

### E.1 Principe : adapter, ne pas remplir

Il n'existe pas de « README parfait » universel. La structure ci-dessous est un **catalogue**, pas une liste à cocher. Un script de 50 lignes n'a pas besoin d'une section « Architecture » ni d'une « Roadmap » ; une bibliothèque a besoin d'une référence d'API qu'une application n'a pas.

Trois règles pour choisir :

1. **Pose-toi la question du lecteur :** « qui ouvre ce dépôt, et que cherche-t-il ? ». Écris les sections qui répondent à ça.
2. **Une section vide ou fictive est pire qu'une section absente.** Pas de « Roadmap : à venir » si rien n'est prévu.
3. **Ce qui est long va dans `docs/`**, avec un lien depuis le README.

### E.2 Vue d'ensemble : sections, statut et ordre

Légende : **O** = obligatoire (presque toujours), **R** = recommandé, **F** = facultatif (selon le projet).

| # | Section | Rôle en une phrase | Statut |
| --- | --- | --- | --- |
| 1 | [Titre et présentation](#e3-titre-et-présentation) | Nommer le projet | **O** |
| 2 | [Description courte](#e4-description-courte-et-proposition-de-valeur) | Dire ce qu'il fait et pour qui | **O** |
| 3 | [Aperçu visuel](#e5-aperçu-visuel) | Montrer le résultat | R (projets visuels), F sinon |
| 4 | [Fonctionnalités](#e6-fonctionnalités) | Lister ce que le projet sait faire | R |
| 5 | [Démonstration](#e7-démonstration) | Lien vers une démo en ligne | F |
| 6 | [Installation et prérequis](#e8-installation-et-prérequis) | Permettre de lancer le projet | **O** (si exécutable) |
| 7 | [Configuration](#e9-configuration-et-variables-denvironnement) | Expliquer les réglages | R (si configurable) |
| 8 | [Utilisation et exemples](#e10-utilisation-et-exemples) | Montrer comment s'en servir | **O** |
| 9 | [Architecture](#e11-architecture-du-projet) | Expliquer l'organisation du code | F (projets moyens/grands) |
| 10 | [Technologies](#e12-technologies-utilisées) | Lister la pile technique | R |
| 11 | [Commandes disponibles](#e13-commandes-disponibles) | Recenser les scripts utiles | R |
| 12 | [Tests et qualité](#e14-tests-et-qualité) | Dire comment vérifier le projet | R (open source), F sinon |
| 13 | [Déploiement](#e15-déploiement) | Expliquer la mise en production | F |
| 14 | [Roadmap](#e16-roadmap) | Annoncer la suite | F |
| 15 | [Contribution](#e17-contribution) | Inviter et guider les contributeurs | **O** (open source) |
| 16 | [Licence](#e18-licence) | Dire ce qu'on a le droit de faire | **O** (si public) |
| 17 | [Crédits et remerciements](#e19-crédits-et-remerciements) | Reconnaître les apports | F |
| 18 | [FAQ et dépannage](#e20-faq-et-dépannage) | Résoudre les problèmes courants | F |
| 19 | [Contact et liens utiles](#e21-contact-et-liens-utiles) | Dire où poser des questions | R |

**Ordre conseillé :** présentation → aperçu → fonctionnalités → installation → utilisation → configuration → référence/architecture → qualité/déploiement → contribution → licence → crédits → contact. Le principe : **du plus utile au plus accessoire**, les informations de démarrage d'abord, les informations administratives (licence, crédits) ensuite. La spécification *Standard Readme* impose en plus que la **licence soit la dernière section**.

**Table des matières :** pour un README de plus d'une centaine de lignes, ajoute un sommaire cliquable en haut. GitHub en génère aussi un automatiquement (icône « Outline »), mais un sommaire dans le texte aide les lecteurs qui arrivent par un autre site.

### E.3 Titre et présentation

**Utilité :** identifier le projet immédiatement. **Statut : obligatoire.**

- Le titre est le **nom du projet**, identique au nom du dépôt autant que possible.
- Un seul titre de niveau 1.
- Optionnel : logo ou bannière, badges.

`````markdown
# Pomodoro CLI

[![CI](https://github.com/OWNER/pomodoro-cli/actions/workflows/ci.yml/badge.svg)](https://github.com/OWNER/pomodoro-cli/actions)
[![Licence MIT](https://img.shields.io/badge/licence-MIT-green)](LICENSE)
`````

### E.4 Description courte et proposition de valeur

**Utilité :** en une ou deux phrases, dire **ce que c'est**, **pour qui** et **pourquoi c'est utile**. **Statut : obligatoire.** C'est aussi le texte à reprendre dans le champ « description » du dépôt (voir [G.8](#g8-seo-et-découverte-dun-projet)).

| Faible | Fort |
| --- | --- |
| « Un outil de productivité. » | « Pomodoro CLI est un minuteur Pomodoro pour le terminal : lance une session de 25 minutes en une commande et reçois une notification à la fin. » |
| « Projet pour mon école. » | « Application web de réservation de salles pour l'école : consulte les disponibilités et réserve en deux clics. » |

Formule utile : **« [Nom] est un/une [type] qui [action principale] pour [public], sans [irritant] ».**

### E.5 Aperçu visuel

**Utilité :** convaincre en cinq secondes. **Statut : recommandé pour toute interface, application ou outil en ligne de commande ; facultatif pour une bibliothèque.**

````markdown
![Aperçu de Pomodoro CLI dans un terminal](docs/assets/preview.gif)
````

Voir [D.3](#d3-aperçu-visuel-dans-le-readme) et [D.4](#d4-captures-décran-et-gif-de-démonstration).

### E.6 Fonctionnalités

**Utilité :** énumérer ce que le projet fait. **Statut : recommandé.**

Écris des **bénéfices** plutôt que des détails techniques, 4 à 8 puces maximum.

````markdown
## Fonctionnalités

- Sessions de travail et de pause entièrement configurables
- Notifications de bureau sur Linux, macOS et Windows
- Statistiques hebdomadaires exportables en CSV
- Aucune dépendance au runtime
````

### E.7 Démonstration

**Utilité :** laisser essayer sans installer. **Statut : facultatif**, pertinent pour une application web, un bac à sable ou une bibliothèque avec exemple en ligne.

````markdown
## Démonstration

- Démo en ligne : <https://demo.example.com>
- Identifiants de test : `demo@example.com` / `demo` (compte sans donnée réelle)
````

> [!CAUTION]
> N'expose jamais d'identifiants réels, même pour une « démo » : crée un compte dédié, sans privilèges.

### E.8 Installation et prérequis

**Utilité :** permettre à un lecteur de lancer le projet sur une machine propre. **Statut : obligatoire pour tout ce qui s'exécute.**

Contenu attendu :

1. Les **prérequis** (versions exactes de langage/outils, système).
2. Les **commandes** d'installation dans l'ordre.
3. Comment **vérifier** que ça marche.

`````markdown
## Installation

### Prérequis

- [Node.js](https://nodejs.org) 20 ou plus récent
- npm 10 ou plus récent

### Étapes

```bash
git clone https://github.com/OWNER/REPO.git
cd REPO
npm install
```

Vérifie l'installation :

```bash
npm test
```
`````

> [!TIP]
> Pour une bibliothèque publiée, la première commande est souvent `npm install nom-du-paquet` ou `pip install nom-du-paquet` : mets l'installation **via le gestionnaire de paquets** en premier, le clone du dépôt pour les contributeurs ensuite.

### E.9 Configuration et variables d'environnement

**Utilité :** documenter tout ce que l'utilisateur peut ou doit régler. **Statut : recommandé si le projet est configurable.**

Présente un **tableau** : nom, rôle, obligatoire ou non, valeur par défaut. Fournis un fichier `.env.example` **sans secret**.

````markdown
## Configuration

Copie le fichier d'exemple puis adapte-le :

```bash
cp .env.example .env
```

| Variable | Description | Obligatoire | Défaut |
| --- | --- | --- | --- |
| `PORT` | Port d'écoute du serveur | Non | `3000` |
| `DATABASE_URL` | URL de connexion PostgreSQL | Oui | — |
| `API_KEY` | Clé de l'API tierce | Oui | — |
````

### E.10 Utilisation et exemples

**Utilité :** montrer le chemin le plus court entre l'installation et un premier résultat. **Statut : obligatoire.**

Commence par **l'exemple le plus simple possible**, puis ajoute des cas courants. Montre la **sortie attendue**.

`````markdown
## Utilisation

Lance une session de 25 minutes :

```bash
pomodoro start
```

Résultat :

```text
Session démarrée : 25:00
```

Options courantes :

| Option | Effet |
| --- | --- |
| `--work 50` | Durée de travail en minutes |
| `--break 10` | Durée de pause en minutes |
`````

Pour une **bibliothèque**, montre un exemple de code complet qui fonctionne en copier-coller :

`````markdown
```python
from pomodoro import Timer

timer = Timer(work=25, rest=5)
timer.start()
```
`````

### E.11 Architecture du projet

**Utilité :** aider un contributeur à s'orienter. **Statut : facultatif**, utile dès que le projet dépasse quelques fichiers.

Montre une **arborescence commentée** et, si besoin, un diagramme.

`````markdown
## Architecture

```text
.
├── src/
│   ├── cli/          # Point d'entrée et commandes
│   ├── core/         # Logique du minuteur
│   └── notify/       # Notifications par système
├── tests/            # Tests unitaires
└── docs/             # Documentation détaillée
```

```mermaid
flowchart LR
    CLI --> Core --> Notify
```
`````

Pour un projet complexe, crée un fichier `ARCHITECTURE.md` (voir les projets de référence de la section [Sources](#sources-et-inspirations)).

### E.12 Technologies utilisées

**Utilité :** informer sur la pile technique (utile pour un portfolio ou une évaluation). **Statut : recommandé.**

````markdown
## Technologies

| Domaine | Outils |
| --- | --- |
| Langage | TypeScript 5 |
| Front | React, Vite |
| Back | Node.js, Fastify |
| Base de données | PostgreSQL |
| Tests | Vitest, Playwright |
````

Dans un README professionnel, explique brièvement **pourquoi** un choix a été fait quand ce n'est pas évident.

### E.13 Commandes disponibles

**Utilité :** recenser les scripts du projet. **Statut : recommandé.**

````markdown
## Commandes disponibles

| Commande | Description |
| --- | --- |
| `npm run dev` | Serveur de développement avec rechargement |
| `npm run build` | Construit la version de production |
| `npm test` | Exécute les tests |
| `npm run lint` | Vérifie le style du code |
````

### E.14 Tests et qualité

**Utilité :** permettre de vérifier que tout fonctionne et d'évaluer le sérieux du projet. **Statut : recommandé pour l'open source.**

````markdown
## Tests et qualité

```bash
npm test            # tests unitaires
npm run test:e2e    # tests de bout en bout
npm run lint        # analyse statique
```

La CI exécute ces trois commandes à chaque pull request.
````

### E.15 Déploiement

**Utilité :** expliquer comment mettre en ligne. **Statut : facultatif**, pour les applications.

````markdown
## Déploiement

L'application est déployée automatiquement sur la plateforme X à chaque fusion sur `main`.

Pour un déploiement manuel :

1. Construire l'image : `docker build -t mon-app .`
2. Renseigner les variables d'environnement (voir [Configuration](#configuration)).
3. Démarrer : `docker run -p 3000:3000 --env-file .env mon-app`
````

### E.16 Roadmap

**Utilité :** annoncer la direction du projet. **Statut : facultatif.** Ne la crée que si tu as réellement des plans, et mets-la à jour.

````markdown
## Roadmap

- [x] Version 1.0 : sessions et notifications
- [ ] Export des statistiques en CSV
- [ ] Thème sombre pour l'interface
- [ ] Application mobile (à étudier)

Voir les [issues ouvertes](https://github.com/OWNER/REPO/issues) pour la liste complète.
````

### E.17 Contribution

**Utilité :** dire comment participer. **Statut : obligatoire pour un projet qui accepte des contributions.**

````markdown
## Contribution

Les contributions sont les bienvenues.

1. Ouvre une issue pour discuter du changement.
2. Fork le dépôt et crée une branche : `git checkout -b feature/ma-fonctionnalite`.
3. Lance les tests : `npm test`.
4. Ouvre une pull request décrivant le changement.

Détails dans [CONTRIBUTING.md](CONTRIBUTING.md). Ce projet suit un [code de conduite](CODE_OF_CONDUCT.md).
````

Pour un projet qui **n'accepte pas** de contributions, dis-le clairement : « Ce dépôt est fourni en l'état, les pull requests ne sont pas traitées. »

### E.18 Licence

**Utilité :** préciser les droits d'utilisation. Sans licence, par défaut, **personne n'a le droit de réutiliser ton code**. **Statut : obligatoire pour tout projet public.**

````markdown
## Licence

Distribué sous licence MIT. Voir le fichier [LICENSE](LICENSE) pour plus d'informations.
````

Ajoute un fichier `LICENSE` à la racine (GitHub propose des modèles à la création du fichier). Pour choisir, consulte le site *choosealicense.com*.

### E.19 Crédits et remerciements

**Utilité :** reconnaître les sources, les contributeurs, les ressources. **Statut : facultatif.**

````markdown
## Crédits

- Icônes : [Lucide](https://lucide.dev) (licence ISC)
- Inspiré par [pomodoro-technique](https://example.com)
- Merci à toutes les personnes qui ont [contribué](https://github.com/OWNER/REPO/graphs/contributors)
````

### E.20 FAQ et dépannage

**Utilité :** répondre aux questions et erreurs les plus fréquentes. **Statut : facultatif**, à créer à partir de **vraies** questions reçues.

````markdown
## FAQ et dépannage

<details>
<summary><strong>Erreur « EADDRINUSE : port déjà utilisé »</strong></summary>

Un autre programme utilise le port 3000. Change-le : `PORT=3001 npm run dev`.

</details>

<details>
<summary><strong>Les notifications ne s'affichent pas sur Linux</strong></summary>

Installe `libnotify` puis relance le terminal.

</details>
````

### E.21 Contact et liens utiles

**Utilité :** indiquer où poser des questions. **Statut : recommandé.**

````markdown
## Contact

- Questions : [Discussions GitHub](https://github.com/OWNER/REPO/discussions)
- Bugs : [Issues](https://github.com/OWNER/REPO/issues)
- Sécurité : voir [SECURITY.md](SECURITY.md)
- Auteur : [@OWNER](https://github.com/OWNER)
````

N'écris pas d'adresse personnelle si tu ne souhaites pas être contacté par ce biais : un lien vers les issues ou un formulaire suffit.

---

## F. Templates prêts à utiliser

Chaque template est dans un bloc de cinq backticks : **copie le contenu à l'intérieur** (sans la ligne d'ouverture ni de fermeture), colle-le dans ton `README.md`, puis remplace les valeurs en majuscules et supprime ce qui ne s'applique pas.

| Template | Pour… |
| --- | --- |
| [F.1 Minimal](#f1-readme-minimal-pour-un-petit-projet) | Script, exercice, petit projet |
| [F.2 Bibliothèque / API](#f2-readme-pour-une-bibliothèque-ou-une-api) | Paquet réutilisable, SDK, API |
| [F.3 Application web](#f3-readme-pour-une-application-web) | Site, application full-stack |
| [F.4 Open source](#f4-readme-pour-un-projet-open-source) | Projet qui accueille des contributeurs |
| [F.5 Profil GitHub](#f5-readme-de-présentation-de-profil-github) | Dépôt `OWNER/OWNER` |

### F.1 README minimal pour un petit projet

À utiliser quand le projet tient en quelques fichiers. Longueur cible : moins de 40 lignes.

`````markdown
# NOM_DU_PROJET

Une ou deux phrases : ce que fait le projet et pour qui.

## Installation

```bash
git clone https://github.com/OWNER/REPO.git
cd REPO
pip install -r requirements.txt
```

Prérequis : Python 3.12 ou plus récent.

## Utilisation

```bash
python main.py --input exemple.csv
```

Résultat attendu :

```text
12 lignes traitées, 0 erreur.
```

## Licence

MIT. Voir [LICENSE](LICENSE).
`````

### F.2 README pour une bibliothèque ou une API

Priorité : **installation en une ligne**, **exemple minimal qui marche**, **référence** claire.

`````markdown
<h1 align="center">NOM_DE_LA_LIB</h1>

<p align="center">
  Une phrase : ce que la bibliothèque permet de faire, pour qui.
</p>

<p align="center">
  <a href="https://github.com/OWNER/REPO/actions/workflows/ci.yml"><img src="https://github.com/OWNER/REPO/actions/workflows/ci.yml/badge.svg" alt="CI"></a>
  <a href="https://www.npmjs.com/package/NOM_DU_PAQUET"><img src="https://img.shields.io/npm/v/NOM_DU_PAQUET" alt="Version npm"></a>
  <a href="LICENSE"><img src="https://img.shields.io/github/license/OWNER/REPO" alt="Licence"></a>
</p>

## Sommaire

- [Installation](#installation)
- [Démarrage rapide](#démarrage-rapide)
- [Référence de l'API](#référence-de-lapi)
- [Compatibilité](#compatibilité)
- [Contribution](#contribution)
- [Licence](#licence)

## Installation

```bash
npm install NOM_DU_PAQUET
```

## Démarrage rapide

```typescript
import { createClient } from "NOM_DU_PAQUET";

const client = createClient({ apiKey: process.env.API_KEY });

const result = await client.search("exemple");
console.log(result.items);
```

## Référence de l'API

### `createClient(options)`

| Paramètre | Type | Obligatoire | Description |
| --- | --- | --- | --- |
| `apiKey` | `string` | Oui | Clé d'API |
| `timeout` | `number` | Non | Délai en ms (défaut : `5000`) |

Retourne un objet `Client`.

### `client.search(query)`

| Paramètre | Type | Description |
| --- | --- | --- |
| `query` | `string` | Terme recherché |

Retourne une promesse de `{ items: Item[] }`. Lève une `ApiError` si la requête échoue.

## Compatibilité

| Environnement | Versions prises en charge |
| --- | --- |
| Node.js | 20, 22 |
| Navigateurs | Dernières versions de Chrome, Firefox, Safari |

## Contribution

Les issues et pull requests sont bienvenues. Lis d'abord [CONTRIBUTING.md](CONTRIBUTING.md).

## Licence

MIT. Voir [LICENSE](LICENSE).
`````

### F.3 README pour une application web

Priorité : **aperçu**, **lancement en local**, **configuration**, **architecture**, **déploiement**.

`````markdown
# NOM_DE_L_APP

[![CI](https://github.com/OWNER/REPO/actions/workflows/ci.yml/badge.svg)](https://github.com/OWNER/REPO/actions)

Une phrase : ce que fait l'application et pour qui.

![Aperçu de l'application](docs/assets/preview.png)

**Démo :** <https://demo.example.com>

## Fonctionnalités

- Fonctionnalité 1 : bénéfice pour l'utilisateur
- Fonctionnalité 2 : bénéfice pour l'utilisateur
- Fonctionnalité 3 : bénéfice pour l'utilisateur

## Technologies

| Domaine | Outils |
| --- | --- |
| Front | React, Vite, Tailwind CSS |
| Back | Node.js, Fastify |
| Base de données | PostgreSQL |
| Déploiement | Docker, plateforme X |

## Démarrage en local

### Prérequis

- Node.js 20 ou plus récent
- PostgreSQL 16 ou plus récent (ou Docker)

### Installation

```bash
git clone https://github.com/OWNER/REPO.git
cd REPO
npm install
cp .env.example .env
```

### Configuration

Renseigne les variables dans `.env` :

| Variable | Description | Obligatoire |
| --- | --- | --- |
| `DATABASE_URL` | URL de connexion PostgreSQL | Oui |
| `SESSION_SECRET` | Chaîne aléatoire d'au moins 32 caractères | Oui |
| `PORT` | Port du serveur (défaut : `3000`) | Non |

> [!WARNING]
> Ne commite jamais ton fichier `.env`. Il est listé dans `.gitignore`.

### Lancement

```bash
npm run db:migrate
npm run dev
```

L'application est disponible sur <http://localhost:3000>.

## Commandes disponibles

| Commande | Description |
| --- | --- |
| `npm run dev` | Serveur de développement |
| `npm run build` | Build de production |
| `npm test` | Tests unitaires |
| `npm run lint` | Analyse statique |

## Architecture

```text
.
├── client/    # Interface React
├── server/    # API Fastify
├── prisma/    # Schéma et migrations
└── docs/      # Documentation
```

## Déploiement

Chaque fusion sur `main` déclenche un déploiement automatique (voir `.github/workflows/deploy.yml`).

## Licence

MIT. Voir [LICENSE](LICENSE).
`````

### F.4 README pour un projet open source

Priorité : **confiance** (badges utiles, licence, sécurité), **adoption**, **contribution**.

`````markdown
<div align="center">

<img src="docs/assets/logo.svg" alt="Logo de NOM_DU_PROJET" width="120">

# NOM_DU_PROJET

**Une phrase d'accroche qui dit pourquoi le projet existe.**

[![CI](https://github.com/OWNER/REPO/actions/workflows/ci.yml/badge.svg)](https://github.com/OWNER/REPO/actions)
[![Version](https://img.shields.io/github/v/release/OWNER/REPO)](https://github.com/OWNER/REPO/releases)
[![Licence](https://img.shields.io/github/license/OWNER/REPO)](LICENSE)

[Documentation](docs/README.md) · [Signaler un bug](https://github.com/OWNER/REPO/issues/new) · [Discussions](https://github.com/OWNER/REPO/discussions)

</div>

## Sommaire

- [À propos](#à-propos)
- [Démarrage rapide](#démarrage-rapide)
- [Utilisation](#utilisation)
- [Fonctionnalités](#fonctionnalités)
- [Roadmap](#roadmap)
- [Contribuer](#contribuer)
- [Sécurité](#sécurité)
- [Licence](#licence)
- [Remerciements](#remerciements)

## À propos

Deux ou trois paragraphes : le problème résolu, ce qui distingue le projet, à qui il s'adresse.

## Démarrage rapide

```bash
npm install NOM_DU_PAQUET
```

```javascript
import { hello } from "NOM_DU_PAQUET";

console.log(hello("monde"));
```

## Utilisation

Exemples détaillés dans [docs/usage.md](docs/usage.md).

## Fonctionnalités

- Fonctionnalité 1
- Fonctionnalité 2
- Fonctionnalité 3

## Roadmap

- [x] Version 1.0
- [ ] Fonctionnalité prévue 1
- [ ] Fonctionnalité prévue 2

Voir les [issues ouvertes](https://github.com/OWNER/REPO/issues) pour les propositions.

## Contribuer

Les contributions rendent la communauté open source possible, merci !

1. Lis le [guide de contribution](CONTRIBUTING.md) et le [code de conduite](CODE_OF_CONDUCT.md).
2. Choisis une issue étiquetée `good first issue`, ou ouvre-en une pour discuter de ton idée.
3. Fork, crée une branche, propose une pull request.

## Sécurité

Pour signaler une vulnérabilité, **n'ouvre pas d'issue publique** : suis la procédure de [SECURITY.md](SECURITY.md).

## Licence

Distribué sous licence MIT. Voir [LICENSE](LICENSE).

## Remerciements

- [Contributeurs](https://github.com/OWNER/REPO/graphs/contributors)
- Ressource ou projet qui t'a inspiré
`````

### F.5 README de présentation de profil GitHub

Pour l'activer : crée un dépôt **public** dont le nom est **identique à ton nom d'utilisateur** (`OWNER/OWNER`), et ajoute un fichier `README.md` à la racine. GitHub l'affiche en haut de ton profil.

`````markdown
<h1 align="center">Salut, moi c'est PRÉNOM 👋</h1>

<p align="center">
  Étudiant·e / développeur·se — une phrase qui résume ce que tu aimes construire.
</p>

## À propos

- Je travaille actuellement sur [NOM_DU_PROJET](https://github.com/OWNER/REPO)
- J'apprends : Rust, sécurité web
- Je cherche : un stage de 4 mois en développement (début 2027)
- Pose-moi des questions sur : Python, Linux, Git

## Projets mis en avant

| Projet | Description | Technologies |
| --- | --- | --- |
| [Projet 1](https://github.com/OWNER/projet-1) | Ce que fait le projet en une phrase | Python, FastAPI |
| [Projet 2](https://github.com/OWNER/projet-2) | Ce que fait le projet en une phrase | TypeScript, React |
| [Projet 3](https://github.com/OWNER/projet-3) | Ce que fait le projet en une phrase | Go, Docker |

## Technologies

![Python](https://img.shields.io/badge/Python-3776AB?logo=python&logoColor=white)
![TypeScript](https://img.shields.io/badge/TypeScript-3178C6?logo=typescript&logoColor=white)
![Docker](https://img.shields.io/badge/Docker-2496ED?logo=docker&logoColor=white)

## Me contacter

[![LinkedIn](https://img.shields.io/badge/LinkedIn-0A66C2?logo=linkedin&logoColor=white)](https://www.linkedin.com/in/TON-IDENTIFIANT/)
[![Portfolio](https://img.shields.io/badge/Portfolio-000000?logo=vercel&logoColor=white)](https://TON-SITE.example.com)

<!-- Optionnel : carte de statistiques (service tiers, voir la section D.7 du guide) -->
`````

**Conseils pour un profil :**

- Mets en avant **tes meilleurs projets** (3 à 6) plutôt qu'un mur de badges de technologies.
- Garde-le **court** : un recruteur ou un pair y passe moins d'une minute.
- Mets à jour la ligne « en ce moment » quand elle change, sinon retire-la.
- N'y publie pas d'informations personnelles que tu ne voudrais pas voir indexées (adresse, numéro de téléphone).
- Teste en thème sombre et en thème clair (voir [D.12](#d12-compatibilité-avec-le-thème-sombre-et-clair)).

---

## G. Bonnes pratiques avancées

### G.1 Ancres et navigation interne

GitHub crée une ancre pour **chaque titre**. Règles de calcul : minuscules, espaces remplacés par `-`, ponctuation supprimée (les lettres accentuées sont conservées), suffixe `-1`, `-2`… pour les titres en double (voir le tableau en [B.6](#b6-liens-externes-et-internes)).

**Ce qu'il faut savoir :**

- Passe la souris sur un titre : une icône de lien apparaît, **copie l'URL exacte de l'ancre**.
- Renommer un titre **casse** les liens qui y pointent, y compris ceux d'autres dépôts ou de sites externes.
- Les titres en double (par exemple deux `### Installation`) obtiennent des ancres suffixées : évite les doublons, ou utilise des titres explicites.
- Pour une ancre **stable** malgré les changements de titre, pose une ancre manuelle :

````markdown
<a name="installation"></a>
## Installation et prérequis

Renvoi : [aller à l'installation](#installation)
````

- Un bouton « retour en haut » : `[↑ Retour au sommaire](#sommaire)`.
- Pour un sommaire manuel : liste de liens vers les ancres, ou génère-le avec un outil (par exemple `markdown-toc`) et vérifie-le en CI.

### G.2 Liens relatifs dans un dépôt

| Écriture | Signification |
| --- | --- |
| `[x](CONTRIBUTING.md)` | Fichier dans le même dossier que le fichier courant |
| `[x](docs/api.md)` | Sous-dossier |
| `[x](../README.md)` | Dossier parent |
| `[x](/docs/api.md)` | Depuis la **racine du dépôt** |
| `[x](docs/api.md#auth)` | Fichier + ancre |

**Avantages :** GitHub adapte le lien à la **branche** consultée, ils fonctionnent dans les forks et les clones, et ne cassent pas si le dépôt change de nom.

**Limites :** hors de GitHub (npm, PyPI, générateurs de site), un lien relatif peut ne plus fonctionner. Pour un paquet publié, vérifie le rendu sur la page du registre, ou utilise des URL absolues pour les liens et images concernés.

### G.3 README principal et documentation détaillée

Organisation courante pour un projet qui grandit :

```text
.
├── README.md             # Présentation, démarrage rapide, liens
├── CONTRIBUTING.md       # Guide de contribution
├── CODE_OF_CONDUCT.md    # Code de conduite
├── SECURITY.md           # Signalement de vulnérabilités
├── LICENSE               # Licence
├── CHANGELOG.md          # Historique des versions
└── docs/
    ├── README.md         # Sommaire de la documentation
    ├── usage.md
    ├── architecture.md
    └── assets/           # Images de la documentation
```

GitHub reconnaît les fichiers `CONTRIBUTING.md`, `CODE_OF_CONDUCT.md`, `SECURITY.md` et `LICENSE` et les met en avant dans l'interface du dépôt (onglets d'information, lien lors de l'ouverture d'une issue ou d'une pull request).

### G.4 Tableaux complexes et limitations

Les tableaux Markdown sont **volontairement simples**.

| Besoin | Possible en Markdown ? | Solution |
| --- | --- | --- |
| Cellules fusionnées | Non | Tableau HTML avec `colspan` / `rowspan` |
| Liste à puces dans une cellule | Non | `<br>` et des tirets, ou tableau HTML |
| Bloc de code multi-lignes dans une cellule | Non | Code inline + `<br>`, ou texte hors tableau |
| Largeur de colonne fixe | Non | Tableau HTML, ou texte plus court |
| Tableau très large | Défilement horizontal | Transposer, scinder, ou utiliser une liste |
| Retour à la ligne dans une cellule | Oui avec `<br>` | |
| Barre `\|` dans une cellule | Oui avec `\|` | |

Tableau HTML minimal quand Markdown ne suffit pas :

````markdown
<table>
  <tr>
    <th rowspan="2">Plateforme</th>
    <th colspan="2">Support</th>
  </tr>
  <tr>
    <th>Stable</th>
    <th>Bêta</th>
  </tr>
  <tr>
    <td>Linux</td>
    <td>✅</td>
    <td>✅</td>
  </tr>
</table>
````

Dans un tableau HTML, **le Markdown n'est généralement pas interprété** : utilise des balises HTML (`<code>`, `<strong>`) à l'intérieur.

### G.5 Badges dynamiques

Un badge est **dynamique** quand son contenu est calculé à chaque affichage à partir de l'état réel (build, version, couverture). Un badge statique devient faux sans que personne ne s'en rende compte.

| Information | Source recommandée |
| --- | --- |
| État de la CI | Badge natif d'un workflow GitHub Actions |
| Version publiée | Shields.io (`/npm/v/…`, `/pypi/v/…`, `/github/v/release/…`) |
| Licence | Shields.io (`/github/license/OWNER/REPO`) |
| Couverture de tests | Service de couverture (Codecov, Coveralls…) |
| Version minimale du runtime | Badge statique (à mettre à jour avec le projet) ou dynamique depuis le manifeste |

Les routes de Shields.io changent parfois : consulte la documentation du service lors de l'intégration, et vérifie l'image après publication.

### G.6 Organisation des assets

- **Un dossier dédié :** `docs/assets/` (ou `.github/assets/` si tu veux garder la racine propre).
- **Noms clairs, en minuscules, sans espaces :** `architecture-overview.png`, pas `Capture d'écran 2026-03-02 à 14.31.png`.
- **Un format adapté :** SVG pour logos et schémas, PNG pour captures, WebP/JPEG pour photos.
- **Poids maîtrisé :** compresse les images (outils comme `oxipng`, `svgo`), évite les GIF lourds.
- **Variantes thème :** suffixes `-light` / `-dark`.
- **Ne commite pas de fichiers lourds en boucle** : chaque version d'une image volumineuse s'ajoute à l'historique git pour toujours.
- **Source des schémas :** garde le fichier source (par exemple le `.drawio`) à côté de l'export.

### G.7 Lisibilité et maintenance

- **Phrases courtes**, voix active, verbes d'action ; un paragraphe = une idée.
- **Vocabulaire constant :** un même nom pour un même concept dans tout le README.
- **Date ou version** : indique la version pour laquelle le README est écrit quand les commandes changent d'une version à l'autre.
- **Un seul endroit par information :** si un fait est dans `docs/`, le README y renvoie au lieu de le recopier.
- **Mise à jour dans la même pull request que le code :** ajoute une case « README à jour » dans le modèle de pull request (`.github/PULL_REQUEST_TEMPLATE.md`).
- **Revue périodique :** à chaque version majeure, rejoue la procédure d'installation sur une machine ou un conteneur propre.
- **Supprime l'obsolète** plutôt que de le barrer : le dépôt garde l'historique.

### G.8 SEO et découverte d'un projet

GitHub et les moteurs de recherche exploitent plusieurs éléments :

| Élément | Où | Conseil |
| --- | --- | --- |
| **Nom du dépôt** | Réglages | Court, explicite, mot-clé principal si possible |
| **Description** | Page du dépôt (champ « About ») | Une phrase, avec les mots que l'on tape pour chercher ce projet |
| **Topics** | Page du dépôt (« About ») | 5 à 10 thèmes précis (langage, domaine, techno) |
| **Premières lignes du README** | README | Titre et première phrase : ce sont eux que l'on voit d'abord dans les aperçus et les résultats |
| **Titres** | README | Mots-clés naturels, pas de bourrage |
| **Image de partage** | Réglages | 1280 × 640 px, lisible en miniature |
| **Releases et tags** | Onglet Releases | Notes de version régulières |
| **Site web** | Champ « Website » | Documentation ou démo |
| **Liens entrants** | Autres sites | Articles, listes « awesome », blogs |

Écris pour des **humains** d'abord : un README clair et utile est le meilleur levier de visibilité.

### G.9 Internationalisation

- **Choisis une langue principale** (souvent l'anglais pour un projet destiné à une audience internationale, le français pour un projet local ou scolaire).
- Une traduction = un fichier : `README.md` (langue principale) et `README.fr.md`, `README.es.md`…
- Place un **sélecteur de langue** en haut de chaque fichier :

````markdown
[English](README.md) · [Français](README.fr.md) · [Español](README.es.md)
````

- **Garde les traductions synchronisées** ou indique clairement la version de référence (« Cette traduction peut être en retard sur la version anglaise »).
- Le **code, les noms de commandes et de fichiers** ne se traduisent pas ; traduis les commentaires utiles des exemples.
- Pour beaucoup de langues, déplace les traductions dans `docs/i18n/`.

### G.10 Prévention des informations sensibles dans les exemples

Un README est **public** (et copié, indexé, archivé). Considère chaque ligne comme publiée pour toujours.

**Ne mets jamais :**

- Clés d'API, jetons, mots de passe, chaînes de connexion réelles, clés privées.
- Adresses e-mail, numéros de téléphone ou adresses personnelles.
- Adresses IP internes, noms de serveurs, URL d'environnements privés.
- Captures d'écran qui montrent des données réelles (onglets, notifications, barre d'état).

**Utilise à la place :**

| Donnée | Valeur d'exemple |
| --- | --- |
| Clé / jeton | `YOUR_API_KEY`, `<TOKEN>`, `xxxxxxxx` |
| Mot de passe | `change-me` (et dis qu'il faut le changer) |
| Domaine | `example.com`, `example.org` (réservés pour les exemples) |
| Adresse e-mail | `user@example.com` |
| Adresse IP | `192.0.2.10`, `198.51.100.10`, `203.0.113.10` (plages réservées à la documentation) |
| Fichier de config | `.env.example` commité, `.env` dans `.gitignore` |

> [!CAUTION]
> Si un secret a été commité, **le supprimer dans un commit ultérieur ne suffit pas** : il reste dans l'historique. **Révoque et régénère** la clé immédiatement, puis nettoie l'historique si nécessaire.

**Prévention automatique :** active le *secret scanning* de GitHub (réglages de sécurité du dépôt) et, en local, un outil comme **gitleaks** dans un hook de pré-commit.

### G.11 Compatibilité GitHub

À tester avant de publier :

1. **Aperçu de l'éditeur GitHub** (onglet « Preview » lors de l'édition) ou rendu après un push sur une branche.
2. **Thème sombre et thème clair.**
3. **Mobile** (navigateur ou application).
4. **Page du registre** (npm, PyPI, Docker Hub…) si le README y est republié : alertes, Mermaid et HTML ne sont pas toujours rendus.
5. **Fichier tronqué ?** Garde le README bien sous 500 KiB.
6. **Lecture en texte brut** : bouton « Raw » ou `cat README.md` : le fichier doit rester compréhensible, car des outils l'affichent sans rendu.

### G.12 Vérification des liens et des images

| Quoi | Comment |
| --- | --- |
| Liens externes | Outil en ligne de commande ou action CI (par exemple **lychee**, **markdown-link-check**) |
| Liens relatifs et images locales | Les mêmes outils, en mode hors ligne sur le dépôt |
| Ancres internes | Linter Markdown (règle `MD051` de markdownlint) |
| Images présentes | Contrôle manuel ou outil de lien |
| Rendu | Aperçu GitHub après chaque modification importante |

Exemple en local avec lychee (installation à faire selon ton système, voir la documentation du projet) :

```bash
lychee --offline README.md docs/
lychee README.md
```

### G.13 Automatisation des contrôles

Automatise ce qui peut l'être : lint du Markdown, liens, et exécution réelle des commandes documentées.

**1. Règles de lint** : fichier `.markdownlint.json` à la racine (adapte-le à ton style) :

```json
{
  "default": true,
  "MD013": false,
  "MD033": false,
  "MD041": true
}
```

Règles utiles : `MD040` (langage sur les blocs de code), `MD051` (ancres valides), `MD025` (un seul titre de niveau 1), `MD001` (pas de saut de niveau). `MD013` (longueur de ligne) et `MD033` (HTML inline) sont souvent désactivées pour un README.

**2. Workflow GitHub Actions** : `.github/workflows/docs.yml`

```yaml
name: Docs

on:
  pull_request:
    paths:
      - "**/*.md"
      - "docs/**"
  push:
    branches: [main]

jobs:
  markdown:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v4

      - name: Lint Markdown
        uses: DavidAnson/markdownlint-cli2-action@v19
        with:
          globs: "**/*.md"

      - name: Vérifier les liens
        uses: lycheeverse/lychee-action@v2
        with:
          args: --no-progress --max-concurrency 4 "**/*.md"
          fail: true
```

> [!NOTE]
> Les versions des actions (`@v4`, `@v19`, `@v2`) sont données à titre d'exemple : consulte la page de chaque action sur GitHub Marketplace pour utiliser la version courante, et épingle-la.

**3. Tester les commandes du README** : le meilleur contrôle est de les **exécuter** :

- Un job CI qui part d'un conteneur vierge et rejoue `Installation` + `Utilisation`.
- Pour une bibliothèque, des *doctests* ou des tests qui importent les exemples du README.
- Un script qui extrait les blocs `bash` du README et les exécute en environnement jetable.

**4. Revue humaine :** une case « README relu » dans le modèle de pull request reste le meilleur filet de sécurité.

---

## H. Erreurs courantes

Pour chaque erreur : **le problème**, **pourquoi c'est gênant**, **la correction**.

### H.1 README vide ou trop court

- **Problème :** juste le titre, ou une phrase (« Projet de test »).
- **Pourquoi :** le lecteur ne sait ni ce que fait le projet, ni comment l'utiliser. Il part.
- **Correction :** ajoute au minimum description, installation, utilisation, licence (modèle [F.1](#f1-readme-minimal-pour-un-petit-projet)).

### H.2 README excessivement long et désorganisé

- **Problème :** 1 200 lignes sans sommaire, tout au même niveau.
- **Pourquoi :** on ne trouve rien ; le fichier approche la limite de troncature.
- **Correction :** sommaire en haut, `docs/` pour les détails, `<details>` pour le secondaire, un lien par sujet.

### H.3 Absence d'installation ou d'exemples

- **Problème :** « Installez les dépendances et lancez. » (lesquelles ? comment ?)
- **Pourquoi :** le lecteur ne peut pas démarrer.
- **Correction :** prérequis avec versions, commandes exactes, exemple minimal et sortie attendue ([E.8](#e8-installation-et-prérequis), [E.10](#e10-utilisation-et-exemples)).

### H.4 Mauvaise utilisation des titres

- **Problème :** plusieurs `#`, niveaux sautés, titres utilisés pour grossir du texte, titres vagues (« Divers »).
- **Pourquoi :** plan latéral inutilisable, accessibilité dégradée, ancres imprévisibles.
- **Correction :**

````markdown
# Nom du projet          <- un seul niveau 1
## Installation          <- sections principales
### Prérequis            <- sous-sections
````

### H.5 Blocs de code sans langage

- **Problème :** trois backticks seuls.
- **Pourquoi :** pas de coloration, lecture plus difficile, lint qui échoue (`MD040`).
- **Correction :** ajoute l'identifiant ([C.3](#c3-choisir-le-bon-identifiant-de-langage)) ; `text` pour une sortie sans coloration.

### H.6 Liens cassés

- **Problème :** pages supprimées, ancres renommées, fichiers déplacés.
- **Pourquoi :** perte de confiance, information inaccessible.
- **Correction :** liens relatifs pour le dépôt, vérification automatique ([G.12](#g12-vérification-des-liens-et-des-images)), ancres manuelles pour les titres cités souvent.

### H.7 Images manquantes

- **Problème :** image non commitée, chemin incorrect, casse différente.
- **Pourquoi :** une icône d'image cassée s'affiche, avec seulement le texte alternatif à la place.
- **Correction :** vérifie `git status`, la casse (`Docs/` ≠ `docs/`), l'existence du fichier dans le dépôt ; ajoute un texte alternatif utile.

### H.8 Badges inutiles

- **Problème :** une dizaine de badges décoratifs, ou un badge statique « build passing ».
- **Pourquoi :** bruit visuel, informations fausses, temps de chargement.
- **Correction :** garde 3 à 6 badges dynamiques et utiles ([D.1](#d1-badges)).

### H.9 Informations obsolètes

- **Problème :** commandes d'une ancienne version, fonctionnalité supprimée, version de Node périmée.
- **Pourquoi :** les lecteurs perdent du temps, les nouveaux utilisateurs échouent à l'installation.
- **Correction :** mise à jour dans la même PR que le code, test en CI, revue à chaque version majeure ([G.7](#g7-lisibilité-et-maintenance)).

### H.10 Commandes non testées

- **Problème :** commandes écrites de mémoire ou depuis une machine déjà configurée.
- **Pourquoi :** elles échouent chez les autres (dépendance implicite, variable oubliée).
- **Correction :** rejoue le README **à froid**, dans un conteneur ou une machine vierge ; automatise ([G.13](#g13-automatisation-des-contrôles)).

### H.11 Clés API ou secrets exposés

- **Problème :** `API_KEY=sk_live_…` réel, `.env` commité, capture d'écran avec jeton.
- **Pourquoi :** compromission de comptes et de données, parfois facturation frauduleuse ; des robots scrutent GitHub en permanence.
- **Correction :** révoque et régénère la clé, remplace par des placeholders, ajoute `.env` au `.gitignore`, active le secret scanning ([G.10](#g10-prévention-des-informations-sensibles-dans-les-exemples)).

### H.12 Markdown mal formé

- **Problème :** bloc de code non fermé, tableau sans ligne de séparation, liste sans ligne vide, balise HTML non fermée.
- **Pourquoi :** le rendu casse, parfois sur tout le reste du fichier.
- **Correction :** prévisualise avant de pousser, lint automatique, reprends les règles de [C.8](#c8-erreurs-de-délimitation-et-backticks-imbriqués) et [B.12](#b12-tableaux).

### H.13 Récapitulatif rapide

| Symptôme visible | Cause probable | Section |
| --- | --- | --- |
| Tout est en code à partir d'un point | Bloc de code non fermé | [C.8](#c8-erreurs-de-délimitation-et-backticks-imbriqués) |
| Le tableau s'affiche comme du texte | Ligne de séparation absente | [B.12](#b12-tableaux) |
| Le texte devient un gros titre | `---` sous une ligne de texte | [B.8](#b8-séparateurs) |
| Pas de saut de ligne | Simple retour à la ligne | [B.3](#b3-paragraphes-et-sauts-de-ligne) |
| Liste cassée après un bloc de code | Bloc non indenté | [B.5](#b5-listes-ordonnées-et-non-ordonnées) |
| Lien interne qui ne mène nulle part | Ancre incorrecte | [G.1](#g1-ancres-et-navigation-interne) |
| Image absente | Chemin ou casse | [H.7](#h7-images-manquantes) |
| Style ignoré | HTML filtré | [B.15](#b15-html-compatible-avec-github) |

---

## I. Checklist finale

Copie cette checklist dans une pull request ou une issue, et coche avant de publier.

**Contenu**

- [ ] Le titre est le nom du projet, un seul `#`.
- [ ] La première phrase dit ce que fait le projet et pour qui.
- [ ] L'installation est décrite avec les prérequis et les versions.
- [ ] Au moins un exemple d'utilisation fonctionne en copier-coller, avec sa sortie.
- [ ] Les sections présentes sont utiles à ce projet (rien d'artificiel).
- [ ] La licence est indiquée et le fichier `LICENSE` existe.
- [ ] La contribution est expliquée (ou l'absence de contribution est dite).
- [ ] Un moyen de poser des questions ou signaler un problème est indiqué.

**Exactitude**

- [ ] Toutes les commandes ont été testées sur une machine ou un conteneur propre.
- [ ] Les versions et prérequis sont à jour.
- [ ] Les exemples correspondent à la version actuelle du code.
- [ ] Aucune information obsolète (fonctionnalité retirée, lien ancien).

**Markdown et mise en forme**

- [ ] Hiérarchie de titres cohérente, sans niveau sauté.
- [ ] Tous les blocs de code sont fermés et ont un langage.
- [ ] Les exemples de Markdown imbriquent correctement leurs backticks.
- [ ] Les tableaux s'affichent (ligne de séparation, bon nombre de colonnes).
- [ ] Les listes sont précédées d'une ligne vide et correctement indentées.
- [ ] Le HTML utilisé est compatible GitHub (pas de `style`, `script`, `iframe`).

**Liens et visuels**

- [ ] Tous les liens externes fonctionnent.
- [ ] Les liens internes (ancres) et relatifs pointent au bon endroit.
- [ ] Toutes les images s'affichent, avec un texte alternatif utile.
- [ ] Les images sont de poids raisonnable ; les GIF sont courts.
- [ ] Les badges sont utiles, dynamiques et en nombre raisonnable.
- [ ] Le rendu est correct en thème clair, sombre et sur mobile.

**Sécurité**

- [ ] Aucun secret, jeton, mot de passe ou clé réelle.
- [ ] Les exemples utilisent des placeholders et des domaines réservés (`example.com`).
- [ ] Aucune donnée personnelle visible dans les captures d'écran.
- [ ] Un `.env.example` est fourni, `.env` est ignoré par git.

**Maintenance**

- [ ] Le README fait moins de 500 KiB, avec un sommaire s'il est long.
- [ ] Les contrôles automatiques (lint, liens) passent.
- [ ] Une relecture par une personne extérieure au projet a eu lieu (test des 30 secondes).

---

## Sources et inspirations

Ce guide est une synthèse originale, construite à partir de ces références (consultées en octobre 2026) :

- GitHub Docs, [À propos des README](https://docs.github.com/en/repositories/managing-your-repositorys-settings-and-features/customizing-your-repository/about-readmes) : emplacements, priorité, limite de 500 KiB, sommaire automatique, liens relatifs.
- GitHub Docs, [Syntaxe de base pour l'écriture et la mise en forme](https://docs.github.com/en/get-started/writing-on-github/getting-started-with-writing-and-formatting-on-github/basic-writing-and-formatting-syntax) : titres, listes, code, images, alertes, échappement, notes de bas de page.
- [Spécification Standard Readme](https://github.com/RichardLitt/standard-readme/blob/main/spec.md) : sections et ordre.
- [awesome-readme](https://github.com/matiassingers/awesome-readme) : README de référence, outils et articles (*Art of Readme*, *Readme Driven Development*, `ARCHITECTURE.md`).
- [Make a README](https://www.makeareadme.com) et [Shields.io](https://shields.io) pour le gabarit et les badges.

> [!NOTE]
> Les services tiers (Shields.io, cartes de statistiques, actions GitHub) évoluent : vérifie leur documentation à jour avant de t'appuyer sur un détail précis.
