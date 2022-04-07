# Analyse_corona

L'objectif du projet est de développer une IA capable de classer les personnes contaminées ou non contaminées au COVID.

Le jeu de données utilisé provient de kaggle, avec plus de 5644 lignes et 39 colonnes.
Dans ce tableau de nombreuses colonnes sont composées de valeurs NaN (valeurs manquantes), la première étape était de nettoyer le tableau en éliminant les colonnes dont le taux de valeur NAN est supérieur à 90%, puis remplacer les valeurs manquantes par 0. 

Après le nettoyage de notre jeu de donnée j’ai essayé de vérifier une hypothèse disant que le nombre de personnes atteintent du COVID dépend de l'âge, et cette hypothèse  s'avérait être vrai, car les personnes âgées de plus de 18 ans et les enfants âgés de 0 ans étaient ceux qui sont les plus atteint par la maladie. 

Suite à ceci j’ai entamé l'étape du preprocessing en faisant l’encodage des données et la sélection de variable pour sélectionner 10 variable sur notre jeu de données ce qui réduit le tableau jusqu'à 10 colonnes puis j’ai divisé le tableau en 2 partie (feature et target), la colonne “SARS-Cov-2 exam result” a été sélectionné pour être le target puisqu'il contient les données montrant qu’une personne est contaminée ou non au COVID afin que les modèles puissent comparer leurs prédictions contre le ce dernier et le feature qui regroupe tous les autres colonnes du tableau  du jeu de données afin  d'entraîner les modèles dessus.

Lors de la modélisation j’ai testé 3 modèles vectorielle: SVC, LinearSVC et SGDClassifier, ils ont été entrainer puis évaluer, le modèle SVC a eu un score d'évaluation de 90%, le SGDClassifier a eu un score de 88% et le LinearClassifier a eu un score de 90%. Mais lorsqu’on vérifie la précision de leurs prédictions le modèle SVC a un score de 0, le modèle SGDClassifier a obtenu un score de 14% , et le modèle LinearClassifier a eu un score de 57%, avec de tels scores de précision sur les prédictions aucun d’eux ne pourrais identifier correctement une personne contaminée donc j’ai utilisé la technique du boosting pour avoir une meilleure prédiction avec le modèle GradientBoostingClassifier, lors de l'évaluation il a obtenu un score de 91% et pour la précision des prediction il a obtenu 60%, donc parmis les différents modèle utilisé pour ce projet il est le plus performant.
