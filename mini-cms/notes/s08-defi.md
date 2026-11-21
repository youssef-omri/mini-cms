# Session 08 - Défi

La route posts.tag utilise {tag:slug} : oui
La page d'un tag n'affiche ni brouillon ni article d'un autre tag : oui
Les tags des cartes sont des liens : oui
L'accueil n'affiche que les tags qui ont au moins un article publié : oui
Les trois nouveaux tests passent et php artisan test est vert : oui

Pourquoi filtrer les tags vides après get() plutôt que d'afficher (0) ?
Afficher un tag avec (0) crée une mauvaise expérience utilisateur (cliquer dessus mène à une page vide et frustrante) et nuit au référencement (SEO) en générant des pages sans contenu. Filtrer les tags vides permet d'avoir une interface propre qui ne propose que des catégories réellement actives.

Combien de requêtes ajoute la liste des tags populaires, et pourquoi pas une par tag ?
Elle n'ajoute qu'une seule requête SQL grâce à l'utilisation de `withCount()`. Eloquent intègre le comptage via une sous-requête SQL optimisée directement dans la requête principale, ce qui évite d'exécuter une requête par tag dans la vue (le problème N+1).