# Modele manuel ou modele AutoML ? (TP05)

| Critere                    | Manuel (rf 500/16)                                   | AutoML (FLAML 90 s)                                  |
|----------------------------|------------------------------------------------------|------------------------------------------------------|
| Famille de modele          | foret aleatoire                                      | <FAMILLE>                                            |
| F1 sur le jeu de test      | 0.8345                                               | 0.8611                                               |
| Temps de recherche machine | 2.9 s                                                | 90.6 s                                               |
| Temps humain (estimation)  | 1 h de reglage au TP2                                | 10 a 15 min pour ecrire et lancer le script          |
| Latence mediane (ms)       | <mediane port 8101>                                  | <mediane port 8100>                                  |
| Latence p95 (ms)           | <p95 port 8101>                                      | <p95 port 8100>                                      |
| Taille du fichier (Mo)     | 13.18                                                | 0.32                                                 |
| Explicabilite              | importance des variables, 500 arbres, profondeur 16  | importance des variables, nombre d'arbres            |

## Decision (5 lignes) : quel modele mettre en production, et pourquoi ?

1. Je mets en production le modele AutoML (<FAMILLE>), promu avec l'alias `production`.
2. Son F1 est de 0.8611 contre 0.8345 pour le modele manuel, soit un gain de 0.0266.
3. Son fichier pese 0.32 Mo contre 13.18 Mo, soit environ 41 fois moins, ce qui allege l'image Docker et le deploiement.
4. Sa latence est de <X> ms en mediane (p95 : <Y> ms) contre <X'> ms (p95 : <Y'> ms) pour le modele manuel, des valeurs <comparables / meilleures / legerement superieures>.
5. Son inconvenient est un temps de recherche de 90.6 s contre 2.9 s et une explicabilite moins directe qu'une foret aleatoire ; je garderais le modele manuel si l'explicabilite ou un entrainement tres rapide devenait prioritaire.