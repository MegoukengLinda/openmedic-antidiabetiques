# Consommation d'antidiabétiques en France (Open Medic 2024)

## Question
Qui consomme des antidiabétiques en France, quels médicaments, et qui les prescrit ?

## Données
Open Medic 2024 (Assurance maladie, extrait du SNDS) : boîtes de médicaments remboursées en pharmacie de ville. Analyse limitée à la classe ATC A10 (« Médicaments du diabète »). Licence Ouverte Etalab.

## Méthode
- Lecture d'un fichier volumineux par morceaux (pandas, `chunksize`) et filtrage de la classe A10 (66 390 lignes)
- Conversion des montants au format français (1.036,90) en nombres
- Agrégations par âge, sexe, molécule, région et spécialité du prescripteur
- Visualisations avec matplotlib

## Résultats clés
- **84 millions de boîtes** remboursées en 2024, pour **1 846 M€**.
- Les **60 ans et plus** concentrent **74 %** des boîtes ; les hommes en représentent 57 %.
- La **metformine** représente **34,6 % des boîtes** mais seulement **5,4 % des dépenses** (3,4 € la boîte), alors que la dapagliflozine est la 1re dépense (303 M€) et que les GLP-1 coûtent 74 à 80 € la boîte.
- Les **médecins généralistes libéraux** prescrivent **76 %** des boîtes, contre 5 % pour les endocrinologues libéraux.

## Limites
- Open Medic compte des boîtes, pas des patients.
- Seule la pharmacie de ville est couverte (pas l'hôpital).
- Pas de diagnostic, et des tranches d'âge larges.
- Les régions ne sont pas comparables sans rapporter les chiffres à la population.

## Pistes d'amélioration
- Comparer 2020 et 2024 (progression des GLP-1).
- Calculer des boîtes par habitant par région (données INSEE).

## Outils
Python, pandas, matplotlib, Google Colab.

## Auteure
Linda MISLANGE MEGOUKENG TEGIEU — élève ingénieure en Ingénierie Médicale et Santé (JUNIA-HEI). [LinkedIn](https://www.linkedin.com/in/megoukeng-tegieu-linda-mislange-94082a389)
