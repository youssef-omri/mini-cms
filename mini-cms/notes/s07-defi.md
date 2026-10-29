# Session 07 - Défi : articles de la même catégorie

La section « Dans la même catégorie » apparaît sous un article publié qui a une catégorie : oui
L'article affiché n'apparaît pas dans sa propre section : oui
Un brouillon de la même catégorie n'apparaît pas : oui
La page s'ouvre sans LazyLoadingViolationException : oui
Le nouveau test passe et php artisan test est vert : oui

Combien de requêtes SQL charge la section, et pourquoi pas une par carte ?

Idéalement, la section charge 1 seule requête SQL principale (ou 2 si on utilise l'Eager Loading pour charger une relation comme l'auteur ou l'image).

On ne fait pas une requête par carte pour éviter le problème du "N+1 Queries". Faire une requête par carte multiplie les allers-retours inutiles avec la base de données, ce qui ralentit considérablement le chargement de la page et sature le serveur lorsque le nombre de cartes ou de visiteurs augmente. Il est beaucoup plus performant de récupérer toutes les données en un seul bloc.