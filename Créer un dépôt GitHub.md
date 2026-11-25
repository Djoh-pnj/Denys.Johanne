# Créer un dépôt GitHub

## 1. Objectif

Cette procédure explique comment créer un dépôt sur GitHub, le relier à un projet enregistré sur son ordinateur et publier ses premiers fichiers.

**Prérequis :**

- Posséder un compte GitHub.
    
- Avoir installé Git sur son ordinateur.
    
- Disposer d'un projet local contenant les fichiers à publier.
    
- Avoir accès à un terminal (Terminal Linux, PowerShell ou Git Bash).
    

## 2. Créer un dépôt sur GitHub

1. Se connecter à [GitHub](https://github.com/).
    
2. Cliquer sur le bouton `+`, puis sur **New repository**.
    
3. Saisir un nom pour le dépôt, par exemple `mon-premier-projet`.
    
4. Choisir la visibilité du dépôt : **Public** pour le rendre visible à tous ou **Private** pour en limiter l'accès.
    
5. Pour cette procédure, laisser les options d'ajout de README, de `.gitignore` et de licence décochées afin de créer un dépôt vide.
    
6. Cliquer sur **Create repository**.
    

**Rôle :** le dépôt distant est créé sur GitHub. Il pourra recevoir les fichiers et l'historique des modifications du projet local.

**Résultat attendu :** GitHub affiche la page du nouveau dépôt et propose une adresse HTTPS, par exemple `https://github.com/mon-compte/mon-premier-projet.git`.

## 3. Ouvrir le projet local dans le terminal

1. Repérer le dossier du projet sur son ordinateur.
    
2. Ouvrir un terminal.
    
3. Se déplacer dans le dossier du projet avec la commande suivante, en remplaçant le chemin par celui de son dossier.
    

```bash
cd chemin/vers/mon-projet
```

**Rôle :** `cd` signifie _change directory_. Cette commande permet de se déplacer dans le dossier souhaité.

**Résultat attendu :** le terminal se trouve dans le dossier contenant les fichiers du projet.

Pour vérifier le contenu du dossier, utiliser :

```bash
ls
```

Cette commande affiche les fichiers et les sous-dossiers présents dans le répertoire courant.

## 4. Initialiser Git dans le projet

Exécuter la commande suivante :

```bash
git init
```

**Rôle :** cette commande initialise un dépôt Git local dans le dossier du projet. Git peut alors suivre les modifications des fichiers.

**Résultat attendu :** Git indique que le dépôt a été initialisé. Un dossier caché nommé `.git` est créé pour stocker l'historique et les informations du dépôt.

## 5. Ajouter les fichiers au suivi de Git

1. Ajouter les fichiers du projet à la zone de préparation :
    

```bash
git add .
```

**Rôle :** `git add .` prépare les fichiers du dossier courant et de ses sous-dossiers pour le prochain commit. Les fichiers exclus par `.gitignore` ne sont normalement pas ajoutés.

2. Vérifier l'état du dépôt :
    

```bash
git status
```

**Rôle :** cette commande affiche les fichiers suivis, modifiés ou prêts à être enregistrés.

**Résultat attendu :** les fichiers ajoutés apparaissent dans la section des modifications prêtes à être validées.

## 6. Enregistrer les premières modifications

Exécuter la commande suivante :

```bash
git commit -m "Premier commit"
```

**Rôle :** `git commit` enregistre un instantané des modifications préparées. L'option `-m` permet d'ajouter un message décrivant cet enregistrement.

**Résultat attendu :** Git confirme la création du commit et affiche des informations sur les fichiers enregistrés.

Si Git demande d'indiquer son identité, configurer son nom et son adresse e-mail :

```bash
git config --global user.name "Mon Nom"
git config --global user.email "mon-adresse@example.com"
```

Remplacer les exemples par ses propres informations, puis relancer la commande `git commit`.

## 7. Relier le projet local au dépôt GitHub

1. Copier l'adresse HTTPS du dépôt créé sur GitHub.
    
2. Dans le terminal, exécuter la commande suivante en remplaçant l'adresse par celle de son propre dépôt :
    

```bash
git remote add origin https://github.com/mon-compte/mon-premier-projet.git
```

**Rôle :** `git remote add origin` associe le dépôt local à un dépôt distant nommé `origin`. L'adresse indique où se trouve ce dépôt sur GitHub.

3. Vérifier l'association :
    

```bash
git remote -v
```

**Résultat attendu :** l'adresse du dépôt apparaît généralement deux fois, pour la récupération (`fetch`) et l'envoi (`push`).

## 8. Publier les fichiers sur GitHub

1. Renommer la branche principale en `main` :
    

```bash
git branch -M main
```

**Rôle :** cette commande renomme la branche courante en `main`.

2. Envoyer les commits sur GitHub :
    

```bash
git push -u origin main
```

**Rôle :** `git push` envoie les commits locaux vers le dépôt distant. L'option `-u` configure le suivi entre la branche locale `main` et la branche distante correspondante.

**Résultat attendu :** Git affiche des informations sur le transfert des données. Les fichiers du projet deviennent visibles sur GitHub.

Si une authentification est demandée, suivre les instructions proposées par GitHub. Ne jamais inscrire son mot de passe ou un jeton d'accès dans les fichiers du projet.

## 9. Vérifier la publication

1. Ouvrir la page du dépôt sur GitHub dans un navigateur.
    
2. Actualiser la page.
    
3. Vérifier que les fichiers du projet apparaissent dans la liste.
    
4. Dans le terminal, exécuter :
    

```bash
git status
```

**Résultat attendu :** le message `nothing to commit, working tree clean` indique qu'il ne reste pas de modification locale non enregistrée. Cela ne suffit pas à prouver que la publication a réussi : il faut aussi vérifier la présence des fichiers sur GitHub.

## 10. Retenir les commandes essentielles

|Commande|Rôle|
|---|---|
|`git init`|Initialiser le dépôt local|
|`git add .`|Préparer les fichiers|
|`git status`|Vérifier l'état du dépôt|
|`git commit -m "Message"`|Enregistrer les modifications|
|`git remote add origin URL`|Relier le dépôt distant|
|`git remote -v`|Vérifier l'adresse distante|
|`git branch -M main`|Nommer la branche principale|
|`git push -u origin main`|Publier les commits sur GitHub|

## 11. Conclusion

Le dépôt GitHub permet de conserver une copie en ligne du projet et de suivre son évolution grâce à Git. Après cette première publication, les prochaines modifications peuvent être envoyées avec les commandes `git add`, `git commit` et `git push`.

**Attention :** avant de publier un projet, vérifier qu'il ne contient aucun mot de passe, jeton d'accès, clé privée ou autre information confidentielle.
