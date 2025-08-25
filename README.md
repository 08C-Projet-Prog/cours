# 📘 420-08C-FX – Projet d'approfondissement en programmation

Site du cours **Projet d'approfondissement en programmation (420-08C-FX)** construit avec **VitePress**.  
Il regroupe les énoncés, grilles, modèles et ressources.

---
## Statut

[![Deploy](https://github.com/08C-Projet-Prog/cours/actions/workflows/deploy.yml/badge.svg)](https://github.com/USERNAME/REPO/actions/workflows/deploy.yml)

[![pages-build-deployment](https://github.com/08C-Projet-Prog/cours/actions/workflows/pages/pages-build-deployment/badge.svg)](https://USERNAME.github.io/REPO/)

---

## ⚙️ Stack
- [VitePress](https://vitepress.dev/) – site statique
- Markdown – rédaction
- GitHub Pages – hébergement

---

## 📂 Structure

- `cours/`
  - `.vitepress/` → Config, thème, CSS
  - `enonces/` → Énoncés (planif, sprint, finalisation…)
  - `grilles/` → Grilles d’évaluation
  - `img/` → Images utilisées dans le site
  - `public/` → Plan de cours et documents
  - `ressources/` → Guides (Scrum, UML, Git…)
  - `templates/` → Modèles à copier
  - `calendrier.md` → Calendrier des remises
  - `horaires.md` → Horaire des suivis
  - `index.md` → Page d’accueil
  - `plan-de-cours.md` → Plan de cours

---

## 🚀 Développement

```bash
npm install        # Installer dépendances
npm run docs:dev   # Lancer serveur local
npm run docs:build # Générer site statique
npm run docs:preview # Prévisualiser
```

## 🌐 Déploiement

- GitHub Pages

- Branch : main

- Build : .vitepress/dist

- Base : /cours/

- Images → /img/

- Personnalisation → .vitepress/theme/custom.css