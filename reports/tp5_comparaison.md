# Modele manuel ou modele AutoML ? (TP05)
| Critere                    | Manuel (rf 500/16)                                   | AutoML (FLAML 90 s)                                  |
|----------------------------|------------------------------------------------------|------------------------------------------------------|
| Famille de modele          | foret aleatoire                                      | <FAMILLE>                                            |
| F1 sur le jeu de test      | 0.8345                                               | 0.8611                                               |
| Temps de recherche machine | 2.9 s                                                | 90.6 s                                               |
| Temps humain (estimation)  | 1 h de reglage au TP2                                | 10 a 15 min pour ecrire et lancer le script          |
| Latence mediane (ms)       | <port 8101>                                          | <port 8100>                                          |
| Latence p95 (ms)           | <port 8101>                                          | <port 8100>                                          |
| Taille du fichier (Mo)     | 13.18                                                | 0.32                                                 |
| Explicabilite              | importance des variables, 500 arbres, profondeur 16  | importance des variables, nombre d'arbres            |

## Decision (5 lignes) : quel modele mettre en production, et pourquoi ?

1. Je mets en production le modele <MANUEL ou AUTOML>.
2. Sur la qualite, son F1 est <X> contre <Y> pour l'autre modele (ecart de <Z>).
3. Sur la latence, sa mediane est de <X> ms (p95 : <Y> ms) contre <X'> ms (p95 : <Y'> ms).
4. Sur la taille et l'explicabilite, <comparer : Mo, nombre d'arbres, importance des variables>.
5. Son principal inconvenient est <...> ; je choisirais l'autre modele si <cas ou ce critere devient prioritaire>.

