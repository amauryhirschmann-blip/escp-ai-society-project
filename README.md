# ESCP AI Society — concept de site

> **Projet étudiant ESCP. Concept non officiel : ce n'est pas le site d'ESCP AI Society.**

Proposition de site immersif pour ESCP AI Society, l'association intercampus d'intelligence artificielle de l'ESCP Business School. Objectifs : faciliter le contact avec les partenaires, mettre en avant les projets réalisés et lancer un programme de mentorat IA.

## Ce que contient le site

- **Univers 3D** : un data center lumineux parcouru au scroll, une pluie de billets « ESCP AI », des tags graffiti et le nœud chrome du logo.
- **Projets réalisés** : les événements publiés sur [@escp.ai](https://www.instagram.com/escp.ai/) (KPMG, Accio Work, Utopia ESSEC…), avec un lien vers chaque post.
- **Agenda** : le prochain événement toujours visible, un calendrier du mois et l'ajout en un clic à Google Agenda, Outlook ou au calendrier de l'ordinateur (fichier `.ics`).
- **Partenaires** : les offres de partenariat et un formulaire de contact.
- **Mentorat IA**, inspiré de la Fondation Florence :
  - parcours **Mentoré** (bleu) : un assistant en 4 étapes pour préparer son dossier, avec la grille d'évaluation du jury ;
  - parcours **Mentor** (rouge) : le formulaire « Devenir Mentor » et les bénéfices pour les entreprises (talents, engagement, RSE).
- **Campus** : chaque ville renvoie vers le compte Instagram de son campus.
- **FAQ** : 18 questions d'étudiants débutants en IA, avec recherche et filtres par thème.

## Fichiers

- `index.html` : le site (tout le code est dans ce fichier) ;
- `404.html` : la page d'erreur personnalisée, servie automatiquement par Vercel ;
- `og-image.jpg` : l'image d'aperçu affichée quand le lien est partagé sur les réseaux ;
- `robots.txt` et `sitemap.xml` : les indications pour les moteurs de recherche.

## Mise en ligne

- **Adresse du site** : [escp-ai-society-project.vercel.app](https://escp-ai-society-project.vercel.app/). Elle est déjà renseignée dans `index.html` (balises `og:` et `canonical`), `robots.txt` et `sitemap.xml`. Si l'adresse change, remplacez-la dans ces trois fichiers.
- **Contact RGPD** : renseigné dans la politique de confidentialité.
- **Mesure d'audience** : activez Web Analytics dans les réglages du projet Vercel, puis redéployez. Le site ne la charge qu'après accord du visiteur, et elle fonctionne sans cookie.

## Checklist de mise en ligne

Pages Confidentialité (RGPD) et CGU, bannière de consentement, aucune clé d'API côté navigateur, HTTPS forcé, balises de partage (Open Graph), favicon, sitemap et robots.txt, textes alternatifs, image compressée, scripts non bloquants, contraste AA, responsive, page 404, liens vérifiés, validation et limites des formulaires, anti-spam (champ piège, délai minimal, une minute entre deux envois), mesure d'audience avec consentement, un seul appel à l'action principal (« Devenir partenaire »).

## Technique

Un seul fichier `index.html`, sans étape de build. Les bibliothèques sont chargées depuis des CDN :
[three.js](https://threejs.org/) 0.160 (3D), [GSAP](https://gsap.com/) 3.12 + ScrollTrigger (animations), [Lenis](https://lenis.darkroom.engineering/) 1.1 (défilement fluide) et Google Fonts. Une connexion internet est donc nécessaire.

## Lancer le site

- **En local** : double-cliquez sur `index.html`.
- **En ligne avec Vercel** : importez ce dépôt dans Vercel (Framework : « Other »), puis cliquez sur « Deploy ».

## Limites de cette version statique

L'envoi des dossiers de mentorés et des candidatures de mentors, l'espace d'analyse des membres, la relecture des dossiers par Claude et l'export CSV fonctionnent uniquement dans la version publiée sur claude.ai, qui fournit la base de données. Ici, les formulaires restent utilisables et le dossier peut être copié, mais il n'est pas envoyé.

## Modifier le contenu

Tout se trouve dans `index.html` :

- textes et sections : le HTML dans `<main>` ;
- couleurs et styles : le bloc `<style>` (variables dans `:root`) ;
- événements de l'agenda : le tableau `EVENTS` dans le script ;
- questions de la FAQ : les blocs `<details class="faq__item">` ;
- comptes Instagram des campus : la liste `.cities`.
