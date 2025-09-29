# Architecture Logicielle

- monolithique => 1 seul gros projet (MVC), micro-services => authentification (SSO), Event-Driven => Winform, Hexa => optimisation séparation des responsabilités, code métier, etc...


# TP 1 :

Faire des recherches sur chacun des 4 types d'architecture cités plus haut. Pour chacun récupérer : 

- Une liste de caractéristiques
- Une définition simple et efficace
- Des exemples d'implémentation (schémas ?)
- Des exemples d'utilisation dans des projets connus
- La liste des sources (liens web) où vous avez trouvé les informations


## Monolithique

### Caractéristiques
- Base de code unique pour exécuter plusieurs fonctions métier
- Se composents généralement d'un front, d'un back et d'une BDD
- Architecture la plus simple
- Adapté pour les systèmes simple
- Si plus de ressources doivent être allouées, c'est tout le système qui prend les ressources => On passe très vite dans du gaspillage de ressources
- Limite l'introduction de nouvelles fonnctionnalités
- Augmente les risques en cas de bug car c'est tout le système qui tombe HS pour une seule ligne au fond du code

- De plus en plus d'applications passent d'une architecture Monolithique à une architecture Micro-serivice

### Définition
Une architecture monolithique représente un système simple, développé sur une même base de code. Généralement constitué d'un front, d'un back et d'une BDD.

### Exemples d'implémentations
![alt text](image.png)

### Cas d'utilisations
- Netflix (monolithe au début mais maintenant passé en micro-services)
- Les CMS (Wordpress, shopify)
- Les applications Legacy (les anciennes versions de Microsoft Office)

### sources
- AWS
- vfunction

## Micro-serives

### Caractéristiques

### Définition

### Exemples d'implémentations

### Cas d'utilisations

### sources

## Event-driven

### Caractéristiques

### Définition

### Exemples d'implémentations

### Cas d'utilisations

### sources

## Hexa

### Caractéristiques

### Définition

### Exemples d'implémentations

### Cas d'utilisations

### sources