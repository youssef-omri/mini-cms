# Session 14 - Défi

Connexion enregistre le jeton toute seule : oui
Créer un article répond 201 sans copier le jeton : oui
Le fichier exporté ne contient aucun jeton : oui

Le dépôt est public. Que risquez-vous si le fichier exporté contient un jeton, et comment l'annuler ?
Toute personne ayant accès au dépôt public peut utiliser ce jeton pour s'authentifier et agir en mon nom (créer, modifier ou supprimer des articles) tant qu'il n'est pas révoqué, car un jeton Sanctum n'expire pas par défaut. Pour l'annuler, il faut appeler la route `POST /api/logout` avec ce jeton ou supprimer directement sa ligne correspondante dans la table `personal_access_tokens` en base de données.

Pourquoi les écritures de l'API passent-elles par les Form Requests et PostPolicy plutôt que par des règles écrites dans Api\PostController ?
Cela permet de centraliser et de réutiliser exactement les mêmes règles de validation et d'autorisation entre le site web et l'API (une seule règle pour deux portes). Ainsi, toute modification apportée à une Form Request ou à `PostPolicy` s'applique automatiquement aux deux interfaces, évitant la duplication de code et garantissant qu'elles ne se contredisent jamais.