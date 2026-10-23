# Formation BRGM — Intelligence artificielle et traitement du langage naturel

**19 au 21 octobre 2026 · Orléans · Redha Moulla**

Ce dépôt rassemble le support de la session, les jeux de données et des notebooks corrigés pour reprendre les notions de classification, de traitement des textes, de clustering, de visualisation et de RAG.

## Accès rapide

| Ressource | Accès | Données nécessaires |
| --- | --- | --- |
| Support de cours — 130 pages | [Ouvrir le PDF](IA_BRGM.pdf) | — |
| TP BRGM : analyse des données et modélisation | [Lire le TP](TP_Analyse_Donn%C3%A9es_BRGM.ipynb) · [Ouvrir dans Colab](https://colab.research.google.com/github/RMoulla/IA_BRGM/blob/main/TP_Analyse_Donn%C3%A9es_BRGM.ipynb) | [customer_churn.csv](customer_churn.csv) |
| TP BRGM : classification de textes et analyse de sentiments | [Lire le TP](TP_Classfication_Reviews_BRGM.ipynb) · [Ouvrir dans Colab](https://colab.research.google.com/github/RMoulla/IA_BRGM/blob/main/TP_Classfication_Reviews_BRGM.ipynb) | [Reviews.csv](Reviews.csv) |
| Clustering de textes et visualisations Plotly | [Lire le notebook](TP_Clustering.ipynb) · [Ouvrir dans Colab](https://colab.research.google.com/github/RMoulla/IA_BRGM/blob/main/TP_Clustering.ipynb) | Corpus 20 Newsgroups, téléchargé par le notebook |
| Visualisation interactive avec Plotly | [Lire le TP](TP_Plotly_Gapminder.ipynb) · [Ouvrir dans Colab](https://colab.research.google.com/github/RMoulla/IA_BRGM/blob/main/TP_Plotly_Gapminder.ipynb) | Gapminder, intégré à Plotly |
| RAG : interroger un document PDF | [Lire le TP](TP_RAG_Github.ipynb) · [Ouvrir dans Colab](https://colab.research.google.com/github/RMoulla/IA_BRGM/blob/main/TP_RAG_Github.ipynb) | [IA_BRGM.pdf](IA_BRGM.pdf) |

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

Les notebooks contiennent le code corrigé. Leurs anciennes sorties ont été effacées : les tableaux et graphiques apparaîtront après exécution. Seul le TP RAG nécessite une clé API, à configurer comme indiqué ci-dessous.

Le TP Plotly charge les données Gapminder avec `px.data.gapminder()` : aucun CSV à importer. Sa dernière cellule crée `plotly_gapminder_2007.html`, un fichier HTML autonome, téléchargeable depuis les fichiers Colab.

La dernière partie du TP d’analyse des données installe **Gradio**, puis lance une interface de prédiction du churn. Une connexion Internet est nécessaire ; la dernière cellule reste active et fournit un lien de partage temporaire.

## Repères pour les exercices

- **Analyse des données BRGM** : exploration de 900 observations, visualisations, modélisation statistique avec `statsmodels`, séparation entraînement/test et prédiction du churn par régression logistique. Évaluation par accuracy, précision, rappel et F1 avec un seuil de 0,5, puis interface Gradio.
- **Classification de textes BRGM** : représentation de 644 avis de jeux vidéo par comptage des mots, séparation entraînement/test, régression logistique, rapport de classification et examen des mots associés aux recommandations positives ou négatives.
- **Clustering** : représentation TF-IDF, K-means, projection par ACP et exploration interactive des documents et des mots dominants avec Plotly.
- **Plotly** : nuages de points, bulles, facettes, animation temporelle, courbes, carte et export HTML.
- **RAG** : extraction du texte d’un PDF, découpage en passages, calcul des embeddings, recherche des passages similaires et génération d’une réponse.

## TP RAG : interroger le support BRGM

1. Ouvrez le [TP RAG dans Colab](https://colab.research.google.com/github/RMoulla/IA_BRGM/blob/main/TP_RAG_Github.ipynb) dans une session dédiée, puis enregistrez votre copie.
2. Téléchargez [IA_BRGM.pdf](IA_BRGM.pdf) et importez-le dans les fichiers Colab en conservant son nom exact.
3. Dans **Secrets**, l’icône en forme de clé dans la barre latérale de Colab, ajoutez `OPENAI_API_KEY`, renseignez votre clé et activez **Accès au notebook**.
4. Exécutez les cellules de haut en bas, en commençant par l’installation des dépendances. Le modèle d’embeddings `all-MiniLM-L6-v2` sera téléchargé automatiquement.

La génération utilise `gpt-4o` via l’API OpenAI : une clé valide et un quota disponible sont nécessaires ; les appels peuvent être facturés. Les passages sélectionnés et la question sont transmis à cette API. Conservez votre clé dans les secrets Colab.

Le document doit contenir du texte sélectionnable : ce TP ne réalise pas de reconnaissance de texte sur les scans. Pour essayer un autre document, importez-le et adaptez la variable `pdf_path`.

## Complément : pluie et glissement de terrain

[Télécharger la simulation interactive](Simulation_BRGM_glissement.html), puis ouvrir le fichier HTML dans un navigateur. Elle illustre l’effet de la pluie, du drainage et du niveau d’eau sur le mouvement d’un versant, à partir d’une adaptation de Bernardie et al. (2015).

Il s’agit d’un exemple pédagogique fondé sur un scénario synthétique, sans calibration sur des observations, et non d’un outil de prévision opérationnelle. La référence scientifique et les hypothèses sont accessibles dans le panneau **Sources**. Une connexion Internet permet de charger les éléments de présentation externes.

## Exécuter les TP sur son ordinateur

Pour les TP d’analyse, de classification, de clustering et de visualisation, ouvrez les notebooks avec Jupyter ou un éditeur compatible, dans le dossier contenant les CSV. Les bibliothèques utilisées sont :

```bash
python -m pip install numpy pandas scikit-learn matplotlib seaborn statsmodels plotly gradio
```

Pour le RAG, utilisez la procédure Colab ci-dessus et sa cellule d’installation : ce notebook emploie `openai==0.28` et les secrets Colab.

## En cas de difficulté

| Problème | Que faire ? |
| --- | --- |
| `FileNotFoundError` | Importer le CSV dans les fichiers Colab et vérifier son nom exact, sans suffixe `(1)` ni extension supplémentaire. |
| Variable inconnue (`NameError`) | Reprendre les cellules depuis le début ou depuis la première cellule en erreur. |
| Bibliothèque manquante (`ModuleNotFoundError`) | Installer la bibliothèque indiquée dans l’environnement Python utilisé. |
| Échec du téléchargement de 20 Newsgroups | Vérifier la connexion Internet, puis relancer la cellule de chargement. |
| Secret RAG introuvable | Vérifier le nom `OPENAI_API_KEY` et activer l’accès au notebook dans Colab. |
| Erreur d’authentification ou de quota API | Vérifier la clé, le quota API et l’accès au modèle indiqué dans le notebook. |
| Résultats disparus après une reconnexion | Réimporter les données, puis réexécuter le notebook. |

Pour toute question : **redha.moulla@axia-conseil.com**.

Pour poursuivre la veille en IA : [Courants de fond](https://redhamoulla.substack.com).
