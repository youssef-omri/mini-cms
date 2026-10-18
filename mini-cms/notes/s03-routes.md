# Session 03 - Routes, contrôleurs et layout

## Défi

URL produite par route('about') :
`http://localhost:8000/a-propos`

URL produite par route('posts.show', 'routes-et-controleurs') :
`http://localhost:8000/posts/routes-et-controleurs`

URL produite par route('posts.archive', 2025) :
`http://localhost:8000/posts/archive/2025`

Pourquoi /posts/archive/abc et /posts/article-inconnu répondent toutes deux 404, et quelle ligne de code en est responsable dans chaque cas ?
- `/posts/archive/abc` : Bloqué par la contrainte `whereNumber('year')` dans `web.php` car "abc" n'est pas un nombre. Le contrôleur n'est pas exécuté.
- `/posts/article-inconnu` : L'URL correspond bien à la route, mais le slug n'existe pas dans le tableau du contrôleur. C'est le `abort(404)` dans `PostController::show` qui se déclenche.

Que se passe-t-il si une vue appelle route('posts.show') sans paramètre ?
Laravel lève une erreur de génération d'URL : `Missing required parameter for [Route: posts.show]`, car l'identifiant de l'article est obligatoire pour générer le lien.