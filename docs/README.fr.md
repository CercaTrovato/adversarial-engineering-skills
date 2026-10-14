# Adversarial Engineering Skills

**Remettre le plan en question. Examiner les changements. Prouver le résultat.**

[English](../README.md) · Français · [Toutes les langues](../README.md)

Une compétence de gestion de l'ingénierie pour les agents de programmation, organisée en trois contrôles de qualité fondés sur des preuves. La personne ou l'agent chargé de la revue doit décrire un scénario d'échec concret ; l'agent principal doit corriger le problème ou justifier son rejet par des preuves.

## Trois contrôles

1. **Plan** : avant une réalisation substantielle, vérifier les contraintes, les contrats d'API et de données, les droits, les transitions d'état, les consommateurs oubliés et la complexité superflue.
2. **Changements** : après chaque lot cohérent et avant sa fusion, examiner le diff réel et les comportements affectés. Ajouter une revue de sécurité si nécessaire.
3. **Acceptation** : avant d'annoncer la fin du travail, étayer les affirmations par des résultats d'exécution actuels ou l'inspection des livrables, en précisant les limites.

Les petites modifications appellent des vérifications légères ; les changements risqués, des regards indépendants et des lots vérifiables. L'auto-revue doit être signalée et ne remplace pas une revue indépendante obligatoire. Un point bloquant non résolu empêche de valider le contrôle. Cette compétence n'autorise ni déploiement ni publication.

## Installation

Avec Git et Node.js/npm disponibles, exécuter depuis le projet cible :

```sh
npx skills add CercaTrovato/adversarial-engineering-skills --skill adversarial-engineering
```

Choisir les agents dans l'interface interactive, ou ajouter `-a claude-code`, `-a codex` ou `-a cursor`. Utiliser `--copy` pour éviter les liens symboliques et `-g` pour une installation au niveau utilisateur. Le [guide d'installation](INSTALL.md) couvre les autres agents, l'installation manuelle et la suppression. La compatibilité suit la liste actuelle de Skills CLI ; elle ne signifie pas que chaque agent a été testé de bout en bout.

## Utilisation

> Utilise adversarial-engineering pour ce changement. Remets le plan en question avant l'implémentation, examine le diff, puis vérifie les critères d'acceptation avant de conclure. Indique le traitement de chaque constat, les preuves et ce qui n'a pas été vérifié.

Pour une revue seule, ajouter « Ne modifie aucun fichier ». Réexaminer les constats concernés par les corrections sans répéter les vérifications dont les preuves restent valides. Un cycle supplémentaire exige de nouvelles preuves ou une correction substantielle.

Le [SKILL.md anglais](../skills/adversarial-engineering/SKILL.md) fait autorité ; cette page présente le fonctionnement et l'installation. Il ne s'agit ni d'une garantie d'absence de défauts ni d'un contrôle CI automatique. Voir la [validation](VALIDATION.md), les [contributions](../CONTRIBUTING.md) et la [licence MIT](../LICENSE). Les corrections de locuteurs natifs sont bienvenues.
