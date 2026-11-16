# TP Git – Gestion des formations

**Auteur :** Adam Doming
**Date :** 16/11/2026
**Dépôts :**
- GitHub : https://github.com/adamdoming7/GestionFormations
- GitLab : https://gitlab.com/adamdoming123/gestionformations

Ce TP simule le travail de deux développeurs (A et B) sur un petit projet web, chacun sur sa propre branche. Il couvre la création de branches, la fusion sans conflit, la création et la résolution d'un conflit, puis l'annulation d'une fusion.

---

## Exercice 1 – Initialisation du dépôt

```bash
mkdir GestionFormations
cd GestionFormations
git init
touch index.html
vi index.html
git add index.html
git commit -m "Initialisation du projet"
git log
```

Contenu initial de `index.html` :

```html
<!DOCTYPE html>
<html>
<head>
  <title>Gestion des formations</title>
</head>
<body>
  <h1>Bienvenue sur notre plateforme</h1>
  <p>Découvrez nos formations.</p>
</body>
</html>
```

Résultat : `[main (root-commit) e860291] Initialisation du projet`

## Exercice 2 – Création et gestion des branches

```bash
git branch accueil
git branch formations
git branch
git switch accueil
git branch                 # * accueil
vi index.html              # ajout de <h2>Votre avenir commence ici !</h2> et d'un <p>
git commit -a -m "Ajout du contenu de la page accueil"
```

Résultat : `[accueil a5f2313] Ajout du contenu de la page accueil`

## Exercice 3 – Travail parallèle sur deux branches

```bash
git switch formations
cat index.html             # le contenu de accueil n'est pas présent
vi index.html              # ajout du <h2> "Nos formations disponibles" et de la liste <ul>
git add .
git commit -m "Ajout de la liste des formations"
git log --oneline --graph --all
```

```
* 496f2c8 (HEAD -> formations) Ajout de la liste des formations
| * a5f2313 (accueil) Ajout du contenu de la page accueil
|/
* e860291 (main) Initialisation du projet
```

## Exercice 4 – Première fusion sans conflit

```bash
git switch main
git merge formations
cat index.html
git log --oneline
```

Résultat : `Updating e860291..496f2c8` puis `Fast-forward`.

**Pourquoi la fusion a-t-elle pu se réaliser sans conflit ?**
`main` n'avait pas avancé depuis la création de `formations`. Git a simplement déplacé le pointeur de `main` (fast-forward), sans avoir deux historiques à combiner.

**Le travail réalisé dans `accueil` est-il automatiquement intégré dans `main` ?**
Non. Seule `formations` a été fusionnée. `accueil` reste une branche séparée tant qu'on ne la fusionne pas explicitement.

**Quelle est la différence entre `git merge` et `git branch` ?**
`git branch` crée, liste ou supprime des branches (des pointeurs vers des commits). `git merge` intègre l'historique d'une autre branche dans la branche courante.

## Exercice 5 – Provoquer volontairement un conflit

**Développeur A** (branche `accueil`) : le `<h1>` devient
`Bienvenue sur notre plateforme de formation professionnelle`.

```bash
git switch accueil
vi index.html
git add .
git commit -m "Travail du developpeur A"      # [accueil 64e2554]
```

**Développeur B** (branche `formations`) : la même ligne devient
`<h1>Découvrez notre catalogue de formations</h1>`.

```bash
git switch formations
vi index.html
git commit -a -m "Travail du developpeur B"   # [formations 0114f75]
```

**Tentative de fusion :**

```bash
git switch main
git merge accueil
```

```
Auto-merging index.html
CONFLICT (content): Merge conflict in index.html
Automatic merge failed; fix conflicts and then commit the result.
```

**Pourquoi Git signale-t-il un conflit ?**
La même zone du fichier a été modifiée différemment dans les deux branches. Git ne peut pas choisir automatiquement quelle version garder.

**Dans quel fichier se trouve le conflit ?**
Dans `index.html`.

**Que signifient les marqueurs `<<<<<<<`, `=======` et `>>>>>>>` ?**
- `<<<<<<< HEAD` marque le début de la version de la branche courante (`main`).
- `=======` sépare les deux versions.
- `>>>>>>> accueil` marque la fin de la version de la branche fusionnée (`accueil`).

## Exercice 6 – Résolution du conflit

Fichier en conflit :

```html
<<<<<<< HEAD
<h1>Bienvenue sur notre plateforme</h1>
<h2>Nos formations disponibles</h2>
<ul>
  <li>Developpement Web</li>
  <li>Developpement Mobile</li>
  <li>Reseaux Informatiques</li>
</ul>
=======
<h1>Bienvenue sur notre plateforme de formation professionnele</h1>
<h2>Votre avenir commence ici</h2>
>>>>>>> accueil
```

Résolution : conservation du `<h1>` demandé (« …formation professionnelle »), des deux `<h2>` et de la liste, puis suppression de tous les marqueurs.

```bash
vi index.html
git add .
git commit -m "Resolution du conflit de fusion"   # [main 5d8ab8d]
git status                                          # working tree clean
```

## Exercice 7 – Annulation d'une fusion

Principe : reproduire un conflit entre deux branches, lancer la fusion, constater le conflit, puis abandonner.

```bash
git switch -c test-abort          # branche de test
vi index.html                     # modifier le <h1>
git commit -am "Test A"
git switch main
vi index.html                     # modifier le même <h1> autrement
git commit -am "Test B"
git merge test-abort              # CONFLICT
git status                        # Unmerged paths
git merge --abort                 # abandonne la fusion
cat index.html                    # retour à l'état d'avant la fusion
git status                        # working tree clean
```

**Quelle commande permet d'abandonner une fusion en cours ?**
`git merge --abort`.

**Cette commande supprime-t-elle la branche concernée ?**
Non. La branche fusionnée existe toujours, intacte.

**Les commits réalisés avant la fusion sont-ils supprimés ?**
Non. Seule la tentative de fusion est annulée. Le dépôt revient à l'état d'avant `git merge`.

## Exercice 8 – Vérification finale

```bash
git branch -a
git branch --show-current
git log --oneline --graph --all --decorate
git status
```

```
*   c43b74f (HEAD -> main, origin/main, gitlab/main) Merge branch 'main' of https://gitlab.com/adamdoming123/gestionformations
|\
| * 2057ce8 Initial commit
*   5d8ab8d Resolution du conflit de fusion
|\
| * 64e2554 (origin/accueil, gitlab/accueil, accueil) Travail du developpeur A
| * a5f2313 Ajout du contenu de la page accueil
| | * 0114f75 (origin/formations, gitlab/formations, formations) Travail du developpeur B
| |/
|/|
* | 496f2c8 Ajout de la liste des formations
|/
* e860291 Initialisation du projet
```

`git status` : `nothing to commit, working tree clean`.

---

## Publication sur GitHub et GitLab

```bash
git remote set-url origin https://github.com/adamdoming7/GestionFormations.git
git push -u origin --all

git remote add gitlab https://gitlab.com/adamdoming123/gestionformations.git
git pull gitlab main --allow-unrelated-histories --no-rebase
git push gitlab main
git push origin main
```

Le `git pull` a été nécessaire car le projet GitLab contenait déjà un commit initial (`README.md`) absent de l'historique local.
