# Session 13 - Défi

/api/posts/3 affiche tags avec des noms : oui
/api/posts ne contient aucun body, /api/posts/3 en contient un : oui
Aucune LazyLoadingViolationException : oui

Pourquoi ne pas envoyer body dans la liste, et qui en profite ?
La liste reste légère : moins d'octets à transmettre, ce qui offre une réponse plus rapide, notamment pour les clients mobiles (téléphones) et les connexions lentes. Le client ne charge le contenu complet que lorsqu'un utilisateur ouvre un article précis.

Un brouillon renvoie 403. Quel avantage aurait un 404 pour un brouillon ?
Un 404 ne révèle pas qu'un brouillon existe à cet identifiant (sécurité / confidentialité), alors qu'un 403 confirme son existence tout en refusant l'accès.