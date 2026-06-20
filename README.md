-ajouts cosmétiques (lignes verticales et horizontales)
-même les viewers peuvent double cliquer pour vérifier quel médecin est dispo sur un poste (dans le planning)
-amélioration du mode clair
-mode impression propre
-pour les admin, toute valeur entrée est injectée au pinceau. 
-le pinceau peut être activé par alt+clic
-corrections cosmétiques



Récapitulatif du système Sandbox

Création : copie d'une période du planning réel vers planning_sandbox + photo figée dans planning_sandbox_baseline
Édition : dropdown filtré (exclut les conflits cliniques, signale les absences), mode pinceau, sauvegarde
Visualisation continue : rouge/violet pour les conflits cliniques internes à la sandbox, bleu pour les modifications faites en sandbox
Comparaison à la demande : bouton "🔍 Comparer" qui détecte deux types d'écarts avec le planning réel — les vrais conflits (double édition divergente) et les drifts (le réel a bougé, la sandbox ne le sait pas) — tous deux signalés par un encadré orange avec tooltip explicite
Push sélectif : sélection période + colonnes, analyse fraîche, preview cellule par cellule avec checkbox individuelle (cochée par défaut seulement pour les changements propres), affichage clair de la valeur qui sera effectivement écrite
Suppression : reset complet des 3 tables sandbox

C'est un système avec une vraie gestion de concurrence multi-admin, ce qui n'est pas trivial à faire proprement — le découpage clean/drift/conflict avec sélection manuelle est probablement la partie la plus solide de l'ensemble.
Quelques pistes pour plus tard si tu en ressens le besoin à l'usage :

Extension de la période d'une sandbox existante (tu l'avais mentionné en tout début de conversation — "quitte à ce que l'on puisse étendre les dates si besoin") : pas encore implémenté, on pourrait l'ajouter si tu sens que recréer une sandbox à chaque fois devient pénible
Optimisation des updates de baseline en boucle si tu pushs un jour de très gros volumes (200+ cellules) et que ça devient lent
Indicateur visuel dans la barre d'onglets (badge sur "🧪 Sandbox") si une sandbox active existe, pour que tu ne l'oublies pas en navigant entre les onglets
