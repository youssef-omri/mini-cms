# Session 02 - Git et GitHub

Réponses rédigées avec mes propres mots, puis comparées au corrigé de la page.

## 1. Index et commit

Réponse : `git add` envoie les modifications vers l'index. `git commit` les enregistre définitivement dans le dépôt local.

## 2. Branche et tag

Réponse : Une branche est une ligne de développement mobile qui évolue. Un tag est un repère fixe sur un commit précis pour marquer une version.

## 3. Le fichier .env

Réponse : Il contient les configurations sensibles et mots de passe locaux. Il est masqué par sécurité pour ne pas divulguer les identifiants sur GitHub.

## 4. Le dossier vendor/

Réponse : Il contient les packages installés par Composer. Il est exclu car il est très lourd et se retélécharge facilement via `composer install`.

## 5. Git Credential Manager

Réponse : C'est un outil qui mémorise vos identifiants GitHub pour vous éviter de réécrire votre mot de passe à chaque action.
## 6. Historique depuis lab-01
 
Nombre de commits depuis lab-01 : 2

Fichiers modifiés depuis lab-01 : routes/web.php, resources/views/a-propos.blade.php, README.md, notes/s02-git.md, screenshots/

Ce que git tag -n affiche pour lab-01 : lab-01