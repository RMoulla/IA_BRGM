# Formation BRGM — Intelligence artificielle et traitement du langage naturel

**19 au 21 octobre 2026 · Orléans · Redha Moulla**

Ce dépôt rassemble le support de la session, les jeux de données et des notebooks corrigés pour reprendre les notions de classification, de traitement des textes et de clustering.

## Accès rapide

| Ressource | Accès | Données nécessaires |
| --- | --- | --- |
| Support de cours — 130 pages | [Ouvrir le PDF](IA_BRGM.pdf) | — |
| TP BRGM : analyse des données et modélisation | [Lire le TP](TP_Analyse_Donn%C3%A9es_BRGM.ipynb) · [Ouvrir dans Colab](https://colab.research.google.com/github/RMoulla/IA_BRGM/blob/main/TP_Analyse_Donn%C3%A9es_BRGM.ipynb) | [customer_churn.csv](customer_churn.csv) |
| TP BRGM : classification de textes et analyse de sentiments | [Lire le TP](TP_Classfication_Reviews_BRGM.ipynb) · [Ouvrir dans Colab](https://colab.research.google.com/github/RMoulla/IA_BRGM/blob/main/TP_Classfication_Reviews_BRGM.ipynb) | [Reviews.csv](Reviews.csv) |
| Clustering de textes et visualisations Plotly | [Lire le notebook](TP_Clustering.ipynb) · [Ouvrir dans Colab](https://colab.research.google.com/github/RMoulla/IA_BRGM/blob/main/TP_Clustering.ipynb) | Corpus 20 Newsgroups, téléchargé par le notebook |

Le support peut aussi être [téléchargé directement](https://raw.githubusercontent.com/RMoulla/IA_BRGM/main/IA_BRGM.pdf).

Le cours s’arrête à la diapositive **« LLMs propriétaires vs Open Source »**, incluse.

## Télécharger les fichiers

1. Ouvrez le fichier souhaité dans le tableau ci-dessus.
2. Cliquez sur **Download raw file**, l’icône de téléchargement située au-dessus du fichier. Si le bouton **Raw** affiche le texte, enregistrez ce contenu sur votre ordinateur.
3. Conservez le nom et l’extension du fichier. Les notebooks recherchent les CSV sous les noms exacts indiqués dans le tableau.

Si l’aperçu GitHub d’un notebook ou du PDF ne s’affiche pas, utilisez son lien Colab ou téléchargez le fichier.

## Exécuter les notebooks dans Google Colab

Un notebook (`.ipynb`) alterne explications et cellules de code. GitHub permet de le lire ; Colab permet de l’exécuter dans le navigateur.

1. Connectez-vous à votre compte Google, puis ouvrez le lien **Ouvrir dans Colab** du TP choisi.
2. Sélectionnez **Fichier → Enregistrer une copie dans Drive** pour conserver vos modifications.
3. Cliquez sur **Se connecter** et utilisez un environnement **Python 3 avec CPU**.
4. Pour le churn et l’analyse de sentiments, téléchargez le CSV indiqué dans le tableau. Dans Colab, ouvrez **Fichiers** dans la barre latérale, puis **Importer**, et choisissez ce CSV. Attendez qu’il apparaisse dans `/content/`.
5. Exécutez les cellules **de haut en bas**, avec le bouton ▶ ou **Maj + Entrée**.
6. Lisez les résultats, modifiez une instruction ou un paramètre, puis relancez les cellules concernées pour comparer.

**Ouvrir le notebook depuis GitHub n’importe pas automatiquement ses données.** Après une réinitialisation de la session Colab, importez à nouveau les CSV et réexécutez les cellules.

Le TP de clustering télécharge le corpus public 20 Newsgroups lors du premier appel : une connexion Internet est nécessaire. Il traite 11 314 documents ; le calcul des groupes et de l’ACP peut prendre quelques minutes.

Les notebooks contiennent le code corrigé. Leurs anciennes sorties ont été effacées : les tableaux et graphiques apparaîtront après exécution. Aucune clé API n’est nécessaire pour ces TP.

La dernière partie du TP d’analyse des données installe **Gradio**, puis lance une interface de prédiction du churn. Une connexion Internet est nécessaire ; la dernière cellule reste active et fournit un lien de partage temporaire.

## Repères pour les exercices

- **Analyse des données BRGM** : exploration de 900 observations, visualisations, modélisation statistique avec `statsmodels`, séparation entraînement/test et prédiction du churn par régression logistique. Évaluation par accuracy, précision, rappel et F1 avec un seuil de 0,5, puis interface Gradio.
- **Classification de textes BRGM** : représentation de 644 avis de jeux vidéo par comptage des mots, séparation entraînement/test, régression logistique, rapport de classification et examen des mots associés aux recommandations positives ou négatives.
- **Clustering** : représentation TF-IDF, K-means, projection par ACP et exploration interactive des documents et des mots dominants avec Plotly.

## Complément : pluie et glissement de terrain

[Télécharger la simulation interactive](Simulation_BRGM_glissement.html), puis ouvrir le fichier HTML dans un navigateur. Elle illustre l’effet de la pluie, du drainage et du niveau d’eau sur le mouvement d’un versant, à partir d’une adaptation de Bernardie et al. (2015).

Il s’agit d’un exemple pédagogique fondé sur un scénario synthétique, sans calibration sur des observations, et non d’un outil de prévision opérationnelle. La référence scientifique et les hypothèses sont accessibles dans le panneau **Sources**. Une connexion Internet permet de charger les éléments de présentation externes.

## Exécuter les TP sur son ordinateur

Ouvrez les notebooks avec Jupyter ou un éditeur compatible, dans le dossier contenant les CSV. Les bibliothèques utilisées sont :

```bash
python -m pip install numpy pandas scikit-learn matplotlib seaborn statsmodels plotly gradio
```

## En cas de difficulté

| Problème | Que faire ? |
| --- | --- |
| `FileNotFoundError` | Importer le CSV dans les fichiers Colab et vérifier son nom exact, sans suffixe `(1)` ni extension supplémentaire. |
| Variable inconnue (`NameError`) | Reprendre les cellules depuis le début ou depuis la première cellule en erreur. |
| Bibliothèque manquante (`ModuleNotFoundError`) | Installer la bibliothèque indiquée dans l’environnement Python utilisé. |
| Échec du téléchargement de 20 Newsgroups | Vérifier la connexion Internet, puis relancer la cellule de chargement. |
| Résultats disparus après une reconnexion | Réimporter les données, puis réexécuter le notebook. |

Pour toute question : **redha.moulla@axia-conseil.com**.

Pour poursuivre la veille en IA : [Courants de fond](https://redhamoulla.substack.com).
