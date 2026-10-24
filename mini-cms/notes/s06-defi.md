# Session 06 - Défi : publier et dépublier

La route posts.publication apparaît dans route:list avec le verbe PATCH : oui
Le bouton affiche « Publier » sur un brouillon et « Dépublier » sur un article publié : oui
published_at est rempli à la publication et vidé à la dépublication : oui
Le nouveau test passe et php artisan test est vert : oui

Pourquoi PATCH et pas PUT ni GET pour ce bouton ?

On utilise le verbe PATCH car il s'agit d'une modification partielle de la ressource (on met à jour uniquement l'état de publication sans toucher au reste de l'article). 

- GET ne convient pas car il sert uniquement à récupérer/consulter des données sans modifier la base de données.
- PUT ne convient pas car il sert à remplacer intégralement une ressource par une autre.
-