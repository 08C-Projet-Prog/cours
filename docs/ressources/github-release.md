# Guide — Créer une release GitHub manuelle

## Objectif

Publier une application WPF sur GitHub sous forme de *release manuelle*.  
Cette procédure permet à toute personne de **télécharger et d’exécuter** la version compilée d’une application.

::: tip Conseil
[Suivre la vidéo tutoriel de ce guide.](https://youtu.be/ccaST5fXyA4)
:::

---

## Étapes à suivre

### 1. Compiler l’application en mode Release

1. Ouvrir le projet WPF dans Visual Studio.  
2. Sélectionner la configuration **Release** (au lieu de *Debug*).  
3. Utiliser le menu **Build (générer) > Build Solution (générer la solution) (Ctrl+Shift+B)**.  
4. Repérer le dossier de sortie : `bin\Release\net8.0-windows\`
5. Vérifier que le fichier `.exe` fonctionne correctement avant de poursuivre.

---

### 2. Préparer le dossier à publier

1. Créer un dossier nommé selon la version de l’application, par exemple : `MonApplication-v1.0.0`
2. Copier à l’intérieur le dossier contenant le build (ex. `net8.0-windows`)
3. Si votre application utilise la persistence des données (sql ou csv), créer un sous-dossier `data` dans `MonApplication-v1.0.0` :
```text
MonApplication-v1.0.0/
├── net8.0-windows/
    ├─  ...
    ├─  monapplication.dll
    └── monapplication.exe
└── data/
    └── monapplication.sql (script d'initilisation de BD) / monapplication.csv
```
4. Compresser le dossier en `.zip`
---

### 3. Créer une release sur GitHub

1. Ouvrir la page du dépôt GitHub.  
2. Cliquer sur l’onglet **Releases**.  (dans le sidebar à droite)
3. Sélectionner **Draft a new release**.  
4. Remplir les champs :
- **Tag version** → `v1.0.0`  (créer un nouveau tag / Create new tag)
- **Target** → `main`  
- **Title** → `Version 1.0.0`  
- **Description** → inscrire les nouveautés ou correctifs :
  ```markdown
  Nouveautés :
  - Ajout du module de recherche
  - Amélioration de la performance

  Corrections :
  - Résolution du bogue d’affichage
  ```
5. Glisser le fichier `.zip` dans la section **Attach binaries**.  
6. Cliquer sur **Publish release**.

La page de release sera disponible à une adresse du type : https://github.com/nom-utilisateur/nom-repo/releases/tag/v1.0.0

---

## Cas particulier : application avec base de données

- Si l’application utilise une base de données (par exemple MySQL), la release doit inclure un moyen de la recréer facilement.
- Votre release doit également inclure un fichier de configuration (ex. App.config) contenant les **informations de la chaîne de connexion**. 

### 1. Exporter la base de données

Exemple avec le client SQL **DBeaver** (le principe demeure le même) :

1. Clic droit sur la base de données → **Tools (outils) → Dump database**
2. Dans la fenêtre qui s’ouvre :
   - Cocher :
     - La base de données ciblée
     - Toutes les tables
   - Cliquer sur Suivant
   - Conserver les cases cochées par défaut
   - Sélectionner le **dossier de sortie** (ex. `data/`)
   - Dans le champ **Extra command args**, ajouter :
     ```bash
     --databases monapplication --add-drop-database
     ```
     > Cela inclut automatiquement les instructions `CREATE DATABASE` et `USE monapplication;`
3. Cliquer sur **Start** pour lancer l’export
4. Vérifier que le fichier `.sql` généré est bien dans `data/monapplication.sql`
5. **Faites un test de votre script dans une nouvelle BD.**

Exemple de contenu :
```sql
CREATE DATABASE IF NOT EXISTS monapplication;
USE monapplication;

CREATE TABLE utilisateurs (
 id INT AUTO_INCREMENT PRIMARY KEY,
 nom VARCHAR(100),
 courriel VARCHAR(100)
);

INSERT INTO utilisateurs (nom, courriel) VALUES
('Alice', 'alice@example.com'),
('Bob', 'bob@example.com');
```

### 2. Fichier de configuration
Votre release doit inclure un fichier de configuration (souvent déjà dans le projet une fois généré) contenant la chaîne de connexion à la base de données, afin qu’elle puisse être ajustée facilement.

#### App.config
```xml
<?xml version="1.0" encoding="utf-8" ?>
<configuration>
  <connectionStrings>
    <add name="MySqlConnection"
         connectionString="Server=localhost;Database=monapplication;Uid=root;Pwd=root;" />
  </connectionStrings>
</configuration>
```
#### BD.cs

```csharp
string connString = ConfigurationManager.ConnectionStrings["MySqlConnection"].ConnectionString;
```