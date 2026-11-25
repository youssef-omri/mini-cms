# Session 10 - Robustesse

TagAdminTest contient 5 tests verts : oui
/posts/categorie/inconnue affiche Catégorie introuvable avec le statut 404 : oui
php artisan test est vert : oui

1. Pourquoi le message de messages() l'emporte-t-il sur celui de lang/fr/validation.php ?
Parce que Laravel vérifie en premier s'il existe un message personnalisé dans la Form Request pour ce champ et cette règle. Il n'utilise le fichier `lang/fr/validation.php` que par défaut s'il ne trouve rien de plus précis.

2. Pourquoi phpunit.xml fixe-t-il APP_LOCALE ?
Comme nos tests vérifient désormais des messages en français, `phpunit.xml` permet d'imposer cette langue avant même de lire le fichier `.env`. Cela garantit que les tests passent partout de la même façon, peu importe la configuration locale du poste.

3. Pourquoi CategoryController n'a-t-il besoin d'aucun try/catch ?
Parce que les erreurs sont déjà gérées automatiquement par Laravel en dehors du contrôleur : la Form Request bloque et redirige si les données sont invalides, le route model binding gère la 404 si la catégorie n'existe pas, le middleware renvoie la 503 en lecture seule et le gestionnaire d'exceptions s'occupe d'afficher les pages d'erreur.