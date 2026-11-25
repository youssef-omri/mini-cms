# Session 12 - Défi

1. Pourquoi role n'est-il pas dans #[Fillable], et comment votre contrôleur le modifie-t-il quand même ?
On ne met pas `role` dans `#[Fillable]` pour protéger ce champ contre l'assignation de masse : si un utilisateur ajoute un champ `role=admin` dans une requête (par exemple à l'inscription) ou si le code utilise `$request->all()`, Laravel l'ignorera automatiquement. Pour le changer côté administrateur, le contrôleur assigne directement la propriété sur l'objet (`$user->role = ...`) après validation et autorisation, puis appelle `$user->save()`.

2. Pourquoi le callback de Gate::before doit-il renvoyer null, et non false, pour un auteur ?
Parce que `false` bloque définitivement l'accès : si `Gate::before` renvoyait `false` pour un auteur, Laravel lui refuserait toutes les actions, même modifier ses propres articles. En renvoyant `null`, `Gate::before` ne tranche pas et laisse Laravel vérifier la règle normale dans le Gate ou la `PostPolicy`.