# Projet MaxPar

Projet de parallélisme basé sur les conditions de Bernstein.

Le but du projet est de construire un système capable d'exécuter un ensemble de tâches en parallèle tout en respectant les dépendances entre elles.

---

## Structure du projet

- `maxpar.py` : contient l'implémentation des classes `Task` et `TaskSystem`.
- `test_maxpar.py` : fichier de test qui crée des tâches et exécute le système.

---

## Principe

Chaque tâche possède :
- un nom
- les variables qu'elle lit (`reads`)
- les variables qu'elle écrit (`writes`)
- une fonction `run` qui sera exécutée.

Le système construit un **graphe de dépendances** entre les tâches.

Les dépendances proviennent de deux sources :
1. le **graphe de précédence initial**
2. les **interférences entre tâches** (conditions de Bernstein)

Ensuite le système permet :
- une **exécution séquentielle** (`runSeq`)
- une **exécution parallèle** (`run`)
- l'**affichage du graphe de dépendances** (`draw`)

---

## Lancer le projet

Dans le dossier du projet :

```bash
python test_maxpar.py
