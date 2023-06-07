# Détection de la maladie de Parkinson avec l'optimisation de recherche de baleine et MLP
## Introduction
Ce projet vise à développer un système de détection de la maladie de Parkinson (PD) en utilisant une combinaison de l'optimisation de recherche de baleine (WSA) et d'un modèle Perceptron Multi-Couches (MLP). L'algorithme WSA est utilisé pour optimiser les hyperparamètres du MLP, y compris le nombre de neurones dans les couches cachées, la fonction d'activation pour chaque couche cachée et l'algorithme d'optimisation. Le MLP optimisé est ensuite entraîné sur l'ensemble de données de la parole de la maladie de Parkinson pour classer si un sujet est atteint de la maladie de Parkinson ou non en fonction des caractéristiques acoustiques extraites de leurs signaux vocaux.

## Hybrid.py
Le fichier "**Hybrid.py**" contient la mise en œuvre de l'algorithme WSA et du modèle MLP. Il fournit les fonctions nécessaires pour créer le modèle MLP, évaluer ses performances et effectuer l'optimisation WSA.

## Algorithme WSA
L'algorithme WSA est une technique d'optimisation inspirée de la nature qui imite le comportement des baleines à bosse dans leur recherche de nourriture. Il explore l'espace des paramètres du modèle MLP pour trouver la combinaison optimale d'hyperparamètres qui maximise la précision de la détection de la maladie de Parkinson.

### Fonctions
- **make_model(hidden_neurons, hidden_activation_function, optimizer)**: Cette fonction crée un modèle MLP avec le nombre spécifié de neurones dans chaque couche cachée, la fonction d'activation choisie et l'optimiseur.
- **ordinal_decoder(value, min, max, options)**: Cette fonction convertit une valeur numérique en une valeur ordinale en fonction de la plage et des options fournies. Elle est utilisée pour sélectionner la meilleure fonction d'activation pour le MLP pendant le processus d'optimisation WSA.
- **eval_model(model)**: Cette fonction évalue les performances d'un modèle donné sur l'ensemble de données de la parole de la maladie de Parkinson. Elle entraîne le modèle sur les données d'entraînement et calcule la précision sur les données de test.
- **model_from_wsa(params)**: Cette fonction construit un modèle MLP en utilisant les paramètres générés par l'algorithme WSA. Elle décode les paramètres WSA pour obtenir les neurones cachés, la fonction d'activation cachée et l'optimiseur.
- **model_params_from_wsa(params)**: Cette fonction extrait les neurones cachés, la fonction d'activation cachée et l'optimiseur à partir des paramètres WSA.
- **finesse_function(params)**: Cette fonction sert de fonction objectif pour l'algorithme WSA. Elle évalue la précision du modèle MLP en fonction des paramètres donnés.
## Configuration du modèle MLP
Le modèle MLP est configuré en définissant différentes constantes dans le fichier "**Hybrid.py**". Ces constantes comprennent :

- **OPTIMIZE_HIDDEN_ACTIVATION_FUNCTION** : Un indicateur booléen indiquant s'il faut optimiser la fonction d'activation cachée.
- **OPTIMIZE_OPTIMIZER** : Un indicateur booléen indiquant s'il faut optimiser l'optimiseur.
- **MIN_VALUE et MAX_VALUE** : Les valeurs minimale et maximale pour les paramètres WSA.
- **MAX_EPOCHS** : Le nombre maximum d'époques pour l'entraînement du modèle MLP.
- **BATCH_SIZE** : La taille du lot pour l'entraînement du modèle MLP.
## Interface.py
Le fichier "**Interface.py**" contient le code pour l'interface utilisateur du projet utilisant Streamlit. L'interface permet aux utilisateurs d'interagir avec le modèle MLP et l'algorithme WSA pour optimiser les hyperparamètres.

## Fonctionnement de l'interface
- L'interface Streamlit affiche une description du projet et des informations sur l'ensemble de données de la parole de la maladie de Parkinson.
- Les utilisateurs peuvent ajuster les curseurs pour définir le nombre maximum de neurones, le nombre maximum d'itérations, le nombre de baleines, le nombre maximum d'époques et la taille du lot pour l'algorithme WSA.
- En cliquant sur le bouton "Démarrer l'optimisation", l'interface lance le processus d'optimisation WSA et affiche les résultats en fonction des paramètres choisis.
## Bibliothèques utilisées
- **TensorFlow** : TensorFlow est une bibliothèque populaire d'apprentissage automatique et d'intelligence artificielle. Elle offre une infrastructure flexible pour la création et le déploiement de modèles d'apprentissage en profondeur. Dans ce projet, TensorFlow est utilisé pour construire, entraîner et évaluer le modèle Perceptron Multi-Couches (MLP) utilisé pour détecter la maladie de Parkinson.
- **Streamlit** : Streamlit est une bibliothèque de développement d'interfaces utilisateur conviviales pour les applications de science des données. Elle permet de créer rapidement et facilement des applications Web interactives pour visualiser et partager les résultats d'analyse de données et de modèles d'apprentissage automatique. Dans ce projet, Streamlit est utilisé pour créer une interface utilisateur où les utilisateurs peuvent interagir avec le modèle MLP et l'algorithme WSA pour optimiser les hyperparamètres.
## Conclusion
Ce projet combine avec succès l'algorithme WSA et le modèle MLP pour détecter la maladie de Parkinson en utilisant des caractéristiques acoustiques extraites des signaux vocaux. L'algorithme WSA optimise les hyperparamètres du MLP, et l'application Streamlit fournit une interface conviviale pour visualiser et interagir avec le processus d'optimisation et les résultats finaux.
