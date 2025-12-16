  # Note méthodologique sur les données météorologiques utilisées dans ce projet de Big Data et Cloud Computing


Dans ce projet, les données météorologiques du Sénégal ont été collectées à l’aide de la bibliothèque Meteostat, intégrée à un environnement Spark sur Databricks. Meteostat est une plateforme largement utilisée qui agrège des observations issues principalement de stations météorologiques terrestres (aéroports, stations synoptiques, réseaux nationaux).

Lors de la phase de collecte, il a été constaté que certaines régions du Sénégal ne disposaient pas de données, et que des valeurs manquantes apparaissaient pour certaines variables météorologiques (température, précipitations, vent, pression).

Cette limitation s’explique par plusieurs facteurs en particulier des dépendance aux stations météorologiques physiques car, Meteostat repose essentiellement sur des stations au sol. Or, la distribution spatiale des stations météorologiques en Afrique de l’Ouest, et particulièrement au Sénégal, est hétérogène. Certaines régions disposent de stations actives et bien documentées, tandis que d’autres zones sont peu instrumentées (Fatick, Sédhiou, Thiès, Louga et Kaffrine) ou ont des stations dont les données ne sont pas publiées de manière continue.

Même lorsqu’une station existe, elle peut présenter :
 - des interruptions de mesure,
 - des périodes sans transmission,
ce qui se traduit par des valeurs manquantes dans les séries temporelles.

Il se pourrait aussi que toutes les données météorologiques collectées localement ne soient pas nécessairement rendues accessibles aux plateformes internationales ouvertes comme Meteostat.
Cependant, il est important de souligner que l’objectif principal de ce projet n’est pas uniquement d’obtenir des données parfaitement complètes, mais avant tout d'apprendre à utiliser Apache Spark pour collecter, structurer, contrôler, transformer et analyser de grandes quantités de données météorologiques, puis étudier leur relation avec quelques indicateurs économiques.

Allant de ce principe, la présence de valeurs manquantes est un cas réaliste en science des données car, elle permet de mettre en œuvre des contrôles de qualité, des diagnostics de couverture spatiale et temporelle, et des choix analytiques justifiés.
Ainsi, l’accent est volontairement mis sur l’analyse des données météorologiques elles-mêmes (EDA, agrégations, tendances) avant d’aborder l’étude de leur impact économique.



Pour un lecteur dont l’objectif principal serait l’analyse économique directe, sans passer par une phase  de traitement des données météorologiques, il existe des sources déjà harmonisées, complètes et continues, notamment la NASA, via des projets comme MERRA-2, POWER ou GPM, qui fournit des données météorologiques issues de la télédétection satellitaire.
Ces données présentent plusieurs avantages notamment:
  - une couverture spatiale complète,
  - une séries temporelles continues,
  - des données reconstruites et corrigées à partir de modèles climatiques et d’observations satellites,
  - Elles sont très adaptées aux analyses macroéconomiques et environnementales.

Contrairement aux stations au sol, ces données sont obtenues par des capteurs embarqués sur satellites, combinés à des modèles atmosphériques globaux, produisant des champs climatiques homogènes sur des grilles régulières.

En résumé, le choix de Meteostat est délibéré et cohérent avec les objectifs du projet que sont :

  - apprendre le traitement de données réelles imparfaites,
  - utiliser Spark dans un environnement cloud (Databricks),
  - effectuer des contrôles qualité,
  - comprendre les limites des sources de données,
  - relier climat et économie de manière reproductible.

# Le Dashboard

Le dashboard a été réalisé sur Databricks afin d’offrir une vue complète sur les données météorologiques du Sénégal et leurs tendances, mises en perspective avec certaines données agricoles et économiques. L’objectif est de faciliter la compréhension des patterns existants et d’aider à la prise de décisions dans les domaines de l’agriculture, de la planification économique et de la gestion des ressources. Pour accéder au dashboard, suivez les étapes suivantes en cliquant sur le lien : [Dashboard Databricks](https://dbc-6cde42fe-78ab.cloud.databricks.com/dashboardsv3/01f0d9f77f2917d8bdafe3b09c4e245b/published?o=525931635000554)
Vous y trouverez deux pages principales : la première présente une vue générale de la météo au Sénégal entre 2005 et 2025, tandis que la seconde met en évidence le croisement avec les variables agricoles et économiques. Des widgets de filtrage ont été intégrés pour permettre une exploration interactive et personnalisée des données selon différentes régions, périodes ou indicateurs spécifiques.
