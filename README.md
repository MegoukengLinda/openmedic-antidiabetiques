# Consommation d'antidiabétiques en France (Open Medic 2024)

Deux notebooks :

| Notebook | Contenu | Outils |
|---|---|---|
| [`openmedic_antidiabetiques_2024.ipynb`](openmedic_antidiabetiques_2024.ipynb) | Qui consomme, quels médicaments, qui prescrit | Python, pandas, matplotlib |
| [`openmedic_sql_2024.ipynb`](openmedic_sql_2024.ipynb) | Mêmes résultats recalculés en SQL, puis consommation **par habitant** (jointure avec les populations INSEE) | SQL (SQLite), pandas, matplotlib |

## Question
Qui consomme des antidiabétiques en France, quels médicaments, qui les prescrit, et quelles régions en consomment le plus par habitant ?

## Données
Open Medic 2024 (Assurance maladie, extrait du SNDS) : boîtes de médicaments remboursées en pharmacie de ville. Analyse limitée à la classe ATC A10 (« Médicaments du diabète »). Licence Ouverte Etalab.
Populations régionales au 1er janvier 2024 : [INSEE](https://www.insee.fr/fr/statistiques/7752095).

## Méthode
- Lecture d'un fichier volumineux par morceaux (pandas, `chunksize`) et filtrage de la classe A10 (66 390 lignes)
- Conversion des montants au format français (1.036,90) en nombres
- Agrégations par âge, sexe, molécule, région et spécialité du prescripteur
- Visualisations avec matplotlib
- Analyse SQL : base SQLite de 3 tables, `GROUP BY`, `CASE WHEN`, `HAVING`, sous-requêtes, `JOIN` ; résultats vérifiés en les comparant à l'analyse pandas

## Résultats clés
- **84 millions de boîtes** remboursées en 2024, pour **1 846 M€**.
- Les **60 ans et plus** concentrent **74 %** des boîtes ; les hommes en représentent 57 %.
- La **metformine** représente **34,6 % des boîtes** mais seulement **5,4 % des dépenses** (3,4 € la boîte), alors que la dapagliflozine est la 1re dépense (303 M€) et que les GLP-1 coûtent 74 à 80 € la boîte.
- Les **médecins généralistes libéraux** prescrivent **76 %** des boîtes, contre 5 % pour les endocrinologues libéraux.
- **Par habitant**, l'Outre-mer (1 768 boîtes pour 1 000 habitants) et les Hauts-de-France (1 413) consomment le plus ; l'Île-de-France passe de la 1re place en volume à la 11e par habitant (1 077). Moyenne nationale : 1 226.
- Les insulines représentent 17 % des boîtes mais 29 % des dépenses ; cinq molécules récentes (GLP-1 et insulines) concentrent environ 40 % des dépenses.

## Limites
- Open Medic compte des boîtes, pas des patients.
- Seule la pharmacie de ville est couverte (pas l'hôpital).
- Pas de diagnostic, et des tranches d'âge larges.
- Les taux par habitant ne sont pas standardisés sur l'âge.

## Pistes d'amélioration
- Comparer 2020 et 2024 (progression des GLP-1).
- Standardiser les taux régionaux par âge (populations INSEE par tranche d'âge).

## Outils
Python, pandas, SQL (SQLite), matplotlib, Google Colab.

## Auteure
Linda MISLANGE MEGOUKENG TEGIEU — élève ingénieure en Ingénierie Médicale et Santé (JUNIA-HEI). [LinkedIn](https://www.linkedin.com/in/megoukeng-tegieu-linda-mislange-94082a389)
