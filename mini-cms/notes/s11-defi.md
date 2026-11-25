# Session 11 - Défi

/mes-articles ne montre que mes articles, brouillons compris : oui
Un visiteur qui ouvre /mes-articles arrive sur /connexion : oui
Le cookie remember_web_ apparaît quand la case est cochée : oui
Les deux nouveaux tests passent et php artisan test est vert : oui

Pourquoi partir de $request->user()->posts() plutôt que de Post::where('user_id', $request->user()->id) ?
Parce que la relation Eloquent `posts()` applique déjà automatiquement le filtre sur l'utilisateur connecté. C'est plus court, plus lisible et cela évite toute erreur ou manipulation extérieure permettant d'accéder aux articles d'un autre auteur.

Pourquoi la case remember ne doit-elle pas être dans le tableau passé à Auth::attempt() ?
Parce que `Auth::attempt()` utilise toutes les clés du tableau (à part le mot de passe) pour filtrer les colonnes de la table `users` en base de données. Comme il n'y a pas de colonne `remember` dans `users`, Laravel déclencherait une erreur SQL au lieu de connecter l'utilisateur (elle doit être passée en deuxième argument de `attempt()`).