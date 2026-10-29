# Session 05 - Défi : articles récents sur l'accueil

latestPosts contient au plus 3 articles : oui
Seuls les articles publiés sont transmis à la vue : oui
home.blade.php utilise x-post-card et @forelse : oui
Le nouveau test passe et php artisan test est vert : oui

Pourquoi get() et pas paginate(3) sur la page d'accueil ?
La page d'accueil affiche uniquement un bloc fixe des "Articles récents" limité aux 3 derniers posts. get() est idéal pour récupérer cette liste fixe, alors que paginate() générerait des liens de navigation (Page 1, 2, 3...) qui n'ont pas leur place sur une page d'accueil. Pour voir l'ensemble des articles, l'utilisateur doit aller sur la page dédiée /posts.