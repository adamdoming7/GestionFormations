doming@192:~/Documents/Git$ mkdir GestionFormations
doming@192:~/Documents/Git$ cd GestionFormations
doming@192:~/Documents/Git/GestionFormations$ pwd
/home/doming/Documents/Git/GestionFormations
doming@192:~/Documents/Git/GestionFormations$ git init
Initialized empty Git repository in /home/doming/Documents/Git/GestionFormations/.git/
doming@192:~/Documents/Git/GestionFormations$ touch index.html
doming@192:~/Documents/Git/GestionFormations$ vi index.html
doming@192:~/Documents/Git/GestionFormations$ cat index.html
<!DOCTYPE html>
	<html>
		<head>
			<title>Gestion des formations</title>
		</head>
		<body>
			<h1>Bienvenue sur notre plateforme</h1>
			<p>Decouvrez nos formations</p>
		</body>
	</html>
doming@192:~/Documents/Git/GestionFormations$ git add index.html
doming@192:~/Documents/Git/GestionFormations$ git commit -m "Initialisation du projet"
[main (root-commit) e860291] Initialisation du projet
 1 file changed, 10 insertions(+)
 create mode 100644 index.html
doming@192:~/Documents/Git/GestionFormations$ git log
commit e860291e81cdec7506a62ee3f0b628ab34b2af08 (HEAD -> main)
Author: Adam Doming <adamdoming123@gmail.com>
Date:   Mon Nov 16 22:51:45 2026 +0000

    Initialisation du projet
doming@192:~/Documents/Git/GestionFormations$ git branch accueil
doming@192:~/Documents/Git/GestionFormations$ git branch formations
doming@192:~/Documents/Git/GestionFormations$ git branch
  accueil
  formations
* main
doming@192:~/Documents/Git/GestionFormations$ git switch accueil
Switched to branch 'accueil'
doming@192:~/Documents/Git/GestionFormations$ git branch
* accueil
  formations
  main
doming@192:~/Documents/Git/GestionFormations$ vi index.html
doming@192:~/Documents/Git/GestionFormations$ cat index.html
<!DOCTYPE html>
	<html>
		<head>
			<title>Gestion des formations</title>
		</head>
		<body>
			<h1>Bienvenue sur notre plateforme</h1>
			<h2>Votre avenir commence ici</h2>
			<p>Decouvrez nos formations</p>
			<p>Nous propsons des formations adaptees a vos besoins</p>
		</body>
	</html>
doming@192:~/Documents/Git/GestionFormations$ git commit -a -m "Ajout du contenu de la page accueil"
[accueil a5f2313] Ajout du contenu de la page accueil
 1 file changed, 2 insertions(+)
doming@192:~/Documents/Git/GestionFormations$ git log
commit a5f23135c891e3b879c617facdb3e4a5fc5cd493 (HEAD -> accueil)
Author: Adam Doming <adamdoming123@gmail.com>
Date:   Mon Nov 16 22:55:49 2026 +0000

    Ajout du contenu de la page accueil

commit e860291e81cdec7506a62ee3f0b628ab34b2af08 (main, formations)
Author: Adam Doming <adamdoming123@gmail.com>
Date:   Mon Nov 16 22:51:45 2026 +0000

    Initialisation du projet
doming@192:~/Documents/Git/GestionFormations$ git branch formations
fatal: a branch named 'formations' already exists
doming@192:~/Documents/Git/GestionFormations$ git switch formations
Switched to branch 'formations'
doming@192:~/Documents/Git/GestionFormations$ git branch
  accueil
* formations
  main
doming@192:~/Documents/Git/GestionFormations$ cat index.html
<!DOCTYPE html>
	<html>
		<head>
			<title>Gestion des formations</title>
		</head>
		<body>
			<h1>Bienvenue sur notre plateforme</h1>
			<p>Decouvrez nos formations</p>
		</body>
	</html>
doming@192:~/Documents/Git/GestionFormations$ vi index.html
doming@192:~/Documents/Git/GestionFormations$ cat index.html
<!DOCTYPE html>
	<html>
		<head>
			<title>Gestion des formations</title>
		</head>
		<body>
			<h1>Bienvenue sur notre plateforme</h1>
			<h2>Nos formations disponibles</h2>
			<ul>
				<li>Developpement Web</li>
				<li>Developpement Mobile</li>
				<li>Reseaux Informatiques</li>
			</ul>
			<p>Decouvrez nos formations</p>
		</body>
	</html>
doming@192:~/Documents/Git/GestionFormations$ git add .
doming@192:~/Documents/Git/GestionFormations$ git commit -m "Ajout de la liste des formations"
[formations 496f2c8] Ajout de la liste des formations
 1 file changed, 6 insertions(+)
doming@192:~/Documents/Git/GestionFormations$ git log --oneline --graph --all
* 496f2c8 (HEAD -> formations) Ajout de la liste des formations
| * a5f2313 (accueil) Ajout du contenu de la page accueil
|/  
* e860291 (main) Initialisation du projet
doming@192:~/Documents/Git/GestionFormations$ git switch main
Switched to branch 'main'
doming@192:~/Documents/Git/GestionFormations$ git branch
  accueil
  formations
* main
doming@192:~/Documents/Git/GestionFormations$ git merge formations
Updating e860291..496f2c8
Fast-forward
 index.html | 6 ++++++
 1 file changed, 6 insertions(+)
doming@192:~/Documents/Git/GestionFormations$ cat index.html
<!DOCTYPE html>
	<html>
		<head>
			<title>Gestion des formations</title>
		</head>
		<body>
			<h1>Bienvenue sur notre plateforme</h1>
			<h2>Nos formations disponibles</h2>
			<ul>
				<li>Developpement Web</li>
				<li>Developpement Mobile</li>
				<li>Reseaux Informatiques</li>
			</ul>
			<p>Decouvrez nos formations</p>
		</body>
	</html>
doming@192:~/Documents/Git/GestionFormations$ git log
commit 496f2c8e31f41a541c9abbc129f986967b5f2432 (HEAD -> main, formations)
Author: Adam Doming <adamdoming123@gmail.com>
Date:   Mon Nov 16 22:59:30 2026 +0000

    Ajout de la liste des formations

commit e860291e81cdec7506a62ee3f0b628ab34b2af08
Author: Adam Doming <adamdoming123@gmail.com>
Date:   Mon Nov 16 22:51:45 2026 +0000

    Initialisation du projet
doming@192:~/Documents/Git/GestionFormations$ git log --oneline
496f2c8 (HEAD -> main, formations) Ajout de la liste des formations
e860291 Initialisation du projet
doming@192:~/Documents/Git/GestionFormations$ git switch accueil
Switched to branch 'accueil'
doming@192:~/Documents/Git/GestionFormations$ git branch
* accueil
  formations
  main
doming@192:~/Documents/Git/GestionFormations$ vi index.html
doming@192:~/Documents/Git/GestionFormations$ git add .
doming@192:~/Documents/Git/GestionFormations$ git commit -m "Travail du developpeur A"
[accueil 64e2554] Travail du developpeur A
 1 file changed, 1 insertion(+), 1 deletion(-)
doming@192:~/Documents/Git/GestionFormations$ cat index.html
<!DOCTYPE html>
	<html>
		<head>
			<title>Gestion des formations</title>
		</head>
		<body>
			<h1>Bienvenue sur notre plateforme de formation professionnele</h1>
			<h2>Votre avenir commence ici</h2>
			<p>Decouvrez nos formations</p>
			<p>Nous propsons des formations adaptees a vos besoins</p>
		</body>
	</html>
doming@192:~/Documents/Git/GestionFormations$ git switch formations
Switched to branch 'formations'
doming@192:~/Documents/Git/GestionFormations$ vi index.html
doming@192:~/Documents/Git/GestionFormations$ git commit -a -m "Travail du developpeur B"
[formations 0114f75] Travail du developpeur B
 1 file changed, 1 insertion(+), 1 deletion(-)
doming@192:~/Documents/Git/GestionFormations$ git switch accueil
Switched to branch 'accueil'
doming@192:~/Documents/Git/GestionFormations$ git branch
* accueil
  formations
  main
doming@192:~/Documents/Git/GestionFormations$ git merge accueil
Already up to date.
doming@192:~/Documents/Git/GestionFormations$ git switch main
Switched to branch 'main'
doming@192:~/Documents/Git/GestionFormations$ git merge accueil
Auto-merging index.html
CONFLICT (content): Merge conflict in index.html
Automatic merge failed; fix conflicts and then commit the result.
doming@192:~/Documents/Git/GestionFormations$ git remote add origin https://gitlab.com/adamdoming123/tp-gestion-formations.git
doming@192:~/Documents/Git/GestionFormations$ git branch -M main
doming@192:~/Documents/Git/GestionFormations$ git push -uf origin main
Username for 'https://gitlab.com': adamdoming123
Password for 'https://adamdoming123@gitlab.com': 
remote: HTTP Basic: Access denied. If a password was provided for Git authentication, the password was incorrect or you're required to use a token instead of a password. If a token was provided, it was either incorrect, expired, or improperly scoped. See https://gitlab.com/help/topics/git/troubleshooting_git.md#error-on-git-fetch-http-basic-access-denied
fatal: Authentication failed for 'https://gitlab.com/adamdoming123/tp-gestion-formations.git/'
doming@192:~/Documents/Git/GestionFormations$ git push -uf origin main
Username for 'https://gitlab.com': adamdoming123
Password for 'https://adamdoming123@gitlab.com': 
remote: HTTP Basic: Access denied. If a password was provided for Git authentication, the password was incorrect or you're required to use a token instead of a password. If a token was provided, it was either incorrect, expired, or improperly scoped. See https://gitlab.com/help/topics/git/troubleshooting_git.md#error-on-git-fetch-http-basic-access-denied
fatal: Authentication failed for 'https://gitlab.com/adamdoming123/tp-gestion-formations.git/'
doming@192:~/Documents/Git/GestionFormations$ git push -uf origin main
Username for 'https://gitlab.com': adamdoming123
Password for 'https://adamdoming123@gitlab.com': 
remote: HTTP Basic: Access denied. If a password was provided for Git authentication, the password was incorrect or you're required to use a token instead of a password. If a token was provided, it was either incorrect, expired, or improperly scoped. See https://gitlab.com/help/topics/git/troubleshooting_git.md#error-on-git-fetch-http-basic-access-denied
fatal: Authentication failed for 'https://gitlab.com/adamdoming123/tp-gestion-formations.git/'
doming@192:~/Documents/Git/GestionFormations$ git push -uf origin main
Username for 'https://gitlab.com': adamdoming123
Password for 'https://adamdoming123@gitlab.com': 
remote: HTTP Basic: Access denied. If a password was provided for Git authentication, the password was incorrect or you're required to use a token instead of a password. If a token was provided, it was either incorrect, expired, or improperly scoped. See https://gitlab.com/help/topics/git/troubleshooting_git.md#error-on-git-fetch-http-basic-access-denied
fatal: Authentication failed for 'https://gitlab.com/adamdoming123/tp-gestion-formations.git/'
doming@192:~/Documents/Git/GestionFormations$ sudo dnf install gh glab
Place your right thumb on the fingerprint reader
Updating and loading repositories:
Last metadata expiration check: 1:00:16 ago on 2026-11-16 22:16:10.
Repositories loaded.
Package                                                  Arch          Version                                                  Repository                          Size
Installing:
 gh                                                      x86_64        0:2.97.0-1.fc45                                          fedora                          39.6 MiB
 glab                                                    x86_64        0:1.114.0-1.fc45                                         updates                         49.8 MiB

Transaction Summary:
 Installing:         2 packages

Total size of inbound packages is 27 MiB. Need to download 27 MiB.
After this operation, 89 MiB extra will be used (install 89 MiB, remove 0 B).
Warning: A pending offline transaction initiated by the following command will be invalidated: dnf5daemon-server
Is this ok [y/N]: y
[1/2] glab-0:1.114.0-1.fc45.x86_64                                                                                              100% | 530.0 KiB/s |  14.6 MiB |  00m28s
[2/2] gh-0:2.97.0-1.fc45.x86_64                                                                                                 100% | 416.0 KiB/s |  12.0 MiB |  00m29s
------------------------------------------------------------------------------------------------------------------------------------------------------------------------
[2/2] Total                                                                                                                     100% | 846.1 KiB/s |  26.5 MiB |  00m32s
Running transaction
[1/4] Verify package files                                                                                                      100% |  12.0   B/s |   2.0   B |  00m00s
[2/4] Prepare transaction                                                                                                       100% |   5.0   B/s |   2.0   B |  00m00s
[3/4] Installing glab-0:1.114.0-1.fc45.x86_64                                                                                   100% | 191.2 MiB/s |  49.9 MiB |  00m00s
[4/4] Installing gh-0:2.97.0-1.fc45.x86_64                                                                                      100% |  59.0 MiB/s |  39.7 MiB |  00m01s
Warning: Pending offline transaction has been invalidated.
To reschedule, run: dnf5daemon-server
Complete!
doming@192:~/Documents/Git/GestionFormations$ glab auth login
- Signing into gitlab.com
- glab config set -h gitlab.com git_protocol https
✓ Configured Git protocol.
- glab config set -h gitlab.com api_protocol https
✓ Configured API protocol.
✓ Logged in as adamdoming123
✓ Stored your credentials in the operating system keyring.
✓ Configuration saved to /home/doming/.config/glab-cli/config.yml
  - Host: gitlab.com

What's new in glab 1.114.0
  Run: glab whatsnew

A new version of glab is available
  1.114.0 → v1.130.0
  Release notes: https://gitlab.com/gitlab-org/cli/-/releases/v1.130.0
doming@192:~/Documents/Git/GestionFormations$ gh auth login
? Where do you use GitHub? GitHub.com
? What is your preferred protocol for Git operations on this host? HTTPS
? Authenticate Git with your GitHub credentials? Yes
? How would you like to authenticate GitHub CLI? Login with a web browser

! First copy your one-time code: 40EA-6DDC
Press Enter to open https://github.com/login/device in your browser... 
✓ Authentication complete.
- gh config set -h github.com git_protocol https
✓ Configured git protocol
✓ Logged in as adamdoming7
doming@192:~/Documents/Git/GestionFormations$ git push -uf origin main
Enumerating objects: 6, done.
Counting objects: 100% (6/6), done.
Delta compression using up to 8 threads
Compressing objects: 100% (4/4), done.
Writing objects: 100% (6/6), 663 bytes | 663.00 KiB/s, done.
Total 6 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (1/1), done.
remote: GitLab: You are not allowed to force push code to a protected branch on this project.
To https://gitlab.com/adamdoming123/tp-gestion-formations.git
 ! [remote rejected] main -> main (pre-receive hook declined)
error: failed to push some refs to 'https://gitlab.com/adamdoming123/tp-gestion-formations.git'
doming@192:~/Documents/Git/GestionFormations$ git push -u orgin main
fatal: 'orgin' does not appear to be a git repository
fatal: Could not read from remote repository.

Please make sure you have the correct access rights
and the repository exists.
doming@192:~/Documents/Git/GestionFormations$ cat index.html
<!DOCTYPE html>
	<html>
		<head>
			<title>Gestion des formations</title>
		</head>
		<body>
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
			<p>Decouvrez nos formations</p>
			<p>Nous propsons des formations adaptees a vos besoins</p>
		</body>
	</html>
doming@192:~/Documents/Git/GestionFormations$ vi index.html
doming@192:~/Documents/Git/GestionFormations$ vi index.html
doming@192:~/Documents/Git/GestionFormations$ vi index.html
doming@192:~/Documents/Git/GestionFormations$ git add .
doming@192:~/Documents/Git/GestionFormations$ git commit -m "Resolution du conflit de fusion"
[main 5d8ab8d] Resolution du conflit de fusion
doming@192:~/Documents/Git/GestionFormations$ git status
On branch main
nothing to commit, working tree clean
doming@192:~/Documents/Git/GestionFormations$ git merge autre-branche       # Git signale un conflit
git status                    # "Unmerged paths"
git merge --abort             # abandonne la fusion
cat index.html                # retour à l'état d'avant la fusion
git status                    # working tree clean
merge: autre-branche - not something we can merge
On branch main
nothing to commit, working tree clean
fatal: There is no merge to abort (MERGE_HEAD missing).
<!DOCTYPE html>
	<html>
		<head>
			<title>Gestion des formations</title>

		</head>

		<body>

			<h1>Bienvenue sur notre platforme de formation professionnelle</h1>

			<h2>Nos formations disponibles</h2>

			<ul>
				<li>Developpement Web</li>

				<li>Developpement Mobile</li>

				<li>Reseaux Informatiques</li>
			</ul>

			<h2>Votre avenir commence ici</h2>

			<p>Decouvrez nos formations</p>

			<p>Nous propsons des formations adaptees a vos besoins</p>

		</body>

	</html>
On branch main
nothing to commit, working tree clean
doming@192:~/Documents/Git/GestionFormations$ git branch -a                               # toutes les branches
git branch --show-current                   # branche active (ou : git branch)
git log --oneline --graph --all --decorate  # historique graphique
git status                                  # dépôt propre
  accueil
  formations
* main
main
*   5d8ab8d (HEAD -> main) Resolution du conflit de fusion
|\  
| * 64e2554 (accueil) Travail du developpeur A
| * a5f2313 Ajout du contenu de la page accueil
| | * 0114f75 (formations) Travail du developpeur B
| |/  
|/|   
* | 496f2c8 Ajout de la liste des formations
|/  
* e860291 Initialisation du projet
On branch main
nothing to commit, working tree clean
doming@192:~/Documents/Git/GestionFormations$ git remote add origin https://github.com/adamdoming7/GestionFormations.git
git branch -M main
git push -u origin main
error: remote origin already exists.
remote: You are not allowed to push code to this project.
fatal: unable to access 'https://gitlab.com/adamdoming123/tp-gestion-formations.git/': The requested URL returned error: 403
doming@192:~/Documents/Git/GestionFormations$ git remote add origin https://github.com/adamdoming7/GestionFormations.git
git branch -M main
git push -u origin main
error: remote origin already exists.
remote: You are not allowed to push code to this project.
fatal: unable to access 'https://gitlab.com/adamdoming123/tp-gestion-formations.git/': The requested URL returned error: 403
doming@192:~/Documents/Git/GestionFormations$ git remote -v                                                                   # voir les remotes actuels
git remote set-url origin https://github.com/adamdoming7/GestionFormations.git
git remote -v                                                                   # vérifier le changement
git push -u origin --all                                                        # pousse main, accueil et formations
origin	https://gitlab.com/adamdoming123/tp-gestion-formations.git (fetch)
origin	https://gitlab.com/adamdoming123/tp-gestion-formations.git (push)
origin	https://github.com/adamdoming7/GestionFormations.git (fetch)
origin	https://github.com/adamdoming7/GestionFormations.git (push)
Enumerating objects: 18, done.
Counting objects: 100% (18/18), done.
Delta compression using up to 8 threads
Compressing objects: 100% (12/12), done.
Writing objects: 100% (18/18), 1.75 KiB | 1.75 MiB/s, done.
Total 18 (delta 7), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (7/7), done.
To https://github.com/adamdoming7/GestionFormations.git
 * [new branch]      accueil -> accueil
 * [new branch]      formations -> formations
 * [new branch]      main -> main
branch 'accueil' set up to track 'origin/accueil'.
branch 'formations' set up to track 'origin/formations'.
branch 'main' set up to track 'origin/main'.
doming@192:~/Documents/Git/GestionFormations$ cd existing_repo
git remote add origin https://gitlab.com/adamdoming123/gestionformations.git
git branch -M main
git push -uf origin main
bash: cd: existing_repo: No such file or directory
error: remote origin already exists.
branch 'main' set up to track 'origin/main'.
Everything up-to-date
doming@192:~/Documents/Git/GestionFormations$ git remote add gitlab https://gitlab.com/adamdoming123/gestionformations.git
git push -u gitlab --all
Enumerating objects: 18, done.
Counting objects: 100% (18/18), done.
Delta compression using up to 8 threads
Compressing objects: 100% (12/12), done.
Writing objects: 100% (18/18), 1.75 KiB | 1.75 MiB/s, done.
Total 18 (delta 7), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (7/7), done.
remote: 
remote: To create a merge request for accueil, visit:
remote:   https://gitlab.com/adamdoming123/gestionformations/-/merge_requests/new?merge_request%5Bsource_branch%5D=accueil
remote: 
remote: 
remote: To create a merge request for formations, visit:
remote:   https://gitlab.com/adamdoming123/gestionformations/-/merge_requests/new?merge_request%5Bsource_branch%5D=formations
remote: 
To https://gitlab.com/adamdoming123/gestionformations.git
 * [new branch]      accueil -> accueil
 * [new branch]      formations -> formations
 ! [rejected]        main -> main (fetch first)
branch 'accueil' set up to track 'gitlab/accueil'.
branch 'formations' set up to track 'gitlab/formations'.
error: failed to push some refs to 'https://gitlab.com/adamdoming123/gestionformations.git'
hint: Updates were rejected because the remote contains work that you do not
hint: have locally. This is usually caused by another repository pushing to
hint: the same ref. If you want to integrate the remote changes, use
hint: 'git pull' before pushing again.
hint: See the 'Note about fast-forwards' in 'git push --help' for details.
doming@192:~/Documents/Git/GestionFormations$ git pull gitlab main --allow-unrelated-histories --no-rebase
remote: Enumerating objects: 3, done.
remote: Counting objects: 100% (3/3), done.
remote: Compressing objects: 100% (2/2), done.
remote: Total 3 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
Unpacking objects: 100% (3/3), 2.72 KiB | 2.72 MiB/s, done.
From https://gitlab.com/adamdoming123/gestionformations
 * branch            main       -> FETCH_HEAD
 * [new branch]      main       -> gitlab/main
Merge made by the 'ort' strategy.
 README.md | 93 +++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++++
 1 file changed, 93 insertions(+)
 create mode 100644 README.md
doming@192:~/Documents/Git/GestionFormations$ git push gitlab main
git push origin main
Enumerating objects: 10, done.
Counting objects: 100% (10/10), done.
Delta compression using up to 8 threads
Compressing objects: 100% (4/4), done.
Writing objects: 100% (5/5), 791 bytes | 791.00 KiB/s, done.
Total 5 (delta 1), reused 0 (delta 0), pack-reused 0 (from 0)
remote: Resolving deltas: 100% (1/1), completed with 1 local object.
To https://gitlab.com/adamdoming123/gestionformations.git
   2057ce8..c43b74f  main -> main
Enumerating objects: 6, done.
Counting objects: 100% (6/6), done.
Delta compression using up to 8 threads
Compressing objects: 100% (4/4), done.
Writing objects: 100% (5/5), 3.02 KiB | 3.02 MiB/s, done.
Total 5 (delta 0), reused 0 (delta 0), pack-reused 0 (from 0)
To https://github.com/adamdoming7/GestionFormations.git
   5d8ab8d..c43b74f  main -> main
doming@192:~/Documents/Git/GestionFormations$ git status
git log --oneline --graph --all --decorate
On branch main
Your branch is up to date with 'origin/main'.

nothing to commit, working tree clean
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
doming@192:~/Documents/Git/GestionFormations$ 

