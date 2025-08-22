# GitHub Projects
:::tip [Voir le guide technique pour la création de votre projet](github-project-guide)

:::

GitHub Projects est un outil de gestion de projet visuel intégré directement à GitHub.  
Il permet aux équipes de suivre l’avancement des tâches et d’organiser le développement en lien direct avec les **issues** et les **pull requests**.

GitHub Projects est particulièrement adapté pour :
- Organiser les tâches et fonctionnalités d’un projet
- Suivre les sprints en développement Agile
- Faciliter la collaboration en équipe
- Visualiser l’avancement du projet en un coup d’œil
- Lier les tâches directement au code (issues, branches, PR)

---

## Les Composants Clés de GitHub Projects

### Tableaux (Projects)
Un **Project** représente un projet entier ou un volet de développement.  
Il peut être associé à un dépôt GitHub ou être indépendant (projet global).

![Éditer un récit](../img/project-12.png)

---

### Colonnes (Lists / Status)
Les colonnes permettent de structurer le travail en étapes ou en catégories.  
Exemple typique de workflow pour un projet de ce cours :

- **Backlog** : contient tous les récits utilisateurs ou idées de fonctionnalités.
- **À faire** : contient les tâches sélectionnées pour le sprint.
- **En cours** : contient les tâches en cours de réalisation.
- **Bogues** : contient les anomalies à corriger.
- **Terminée** : contient les tâches finalisées et validées.

---

### Cartes (Cards / Issues)
Chaque carte correspond généralement à une **issue** GitHub ou à une note libre.  
On peut y ajouter : 
- Une description détaillée
- Une checklist (sous-tâches)
- Une date limite (milestone)
- Des étiquettes (priorité, type de tâche)
- Un responsable (assigné à un membre de l’équipe)
- Des discussions liées (via commentaires ou PR)

**Exemple de carte pour une fonctionnalité :**

**Issue : *En tant qu’usager, je veux rechercher un livre par titre afin de trouver rapidement un ouvrage qui m’intéresse.***

- **Colonne** : En cours  
- **Assigné** : Marie  
- **Description** : Permettre la recherche d’un livre par titre, auteur ou catégorie.  
- ✅ **Checklist** :
  - [ ] Interface utilisateur pour la recherche  
  - [ ] Connexion avec la base de données  
  - [ ] Tests de performance  
- 📅 **Milestone** : Sprint 2  

---

## Suivre l’avancement des tâches
- Les développeurs déplacent les cartes entre les colonnes au fur et à mesure de l’avancement.  
- Chaque issue peut être liée à une branche ou une pull request pour assurer le suivi.  
- À la fin de chaque sprint, les cartes sont révisées pour confirmer les fonctionnalités livrées et replanifier celles qui ne sont pas terminées.  


