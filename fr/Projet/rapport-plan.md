# Plan de rapport - Système de recommandation d'images

## 1. Introduction
- Présentation du projet : système de recommandation d'images basé sur les préférences utilisateur
- Objectifs : automatisation de la collecte, analyse et recommandation d'images
- Approche générale : combinaison de techniques de traitement d'image et d'apprentissage automatique

## 2. Sources de données
- Wikidata comme source principale via SPARQL pour les images de voitures concept
- Licences : images sous licence libre de Wikimedia Commons
- Volume de données : ensemble d'environ 100 images avec métadonnées extraites

## 3. Méthodologie
### 3.1 Collecte et préparation des données
- Requêtes SPARQL pour extraire des informations sur les voitures concept
- Téléchargement automatisé des images via l'API Wikidata
- Extraction des métadonnées EXIF et caractéristiques des images

### 3.2 Annotation et traitement des images
- Extraction des couleurs dominantes via KMeans
- Système d'annotation manuelle et automatique (vintage, original, night photo)
- Stockage des métadonnées au format JSON pour chaque image

### 3.3 Analyse des données
- Création de profils utilisateurs basés sur les images préférées
- Analyse des préférences en termes de couleurs, orientation, et tags
- Simulation d'utilisateurs pour tester le système

### 3.4 Système de recommandation
- Approche hybride combinant filtrage basé sur le contenu et filtrage collaboratif
- Métriques de similarité entre profils utilisateurs et images
- Pondération des différentes caractéristiques (couleur, orientation, tags)

## 4. Résultats et évaluation
- Performance du système de recommandation
- Visualisation des préférences utilisateurs et des recommandations
- Métriques d'évaluation : précision, rappel, mesure F1
- Analyse des forces et faiblesses du système

## 5. Conclusion
- Synthèse des réalisations
- Limites du système actuel
- Perspectives d'amélioration et travaux futurs
