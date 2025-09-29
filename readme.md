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

#### Définition :

L'architecture monolithique utilise une base de code unique pour plusieurs fonctions métiers,
chaque service sont interdépendants, ce qui implique que la moindre modification peut avoir des répercussions
sur le reste de l'application.

#### Liste de caractéristique :

- Services interdépendants formant 
- Une unité
- Base de code et environnement unique 
- Volumineux
- Déploiement facile

#### Exemples d'implémentations : 
![monolithique.png](monolithique.png)

#### Des exemples d'utilisation dans des projets connus : 

**Wordpress** utilise l'architecture monolithique
**PrestaShop** utilise l'architecture monolithique

### [Atlassian](https://www.atlassian.com/fr/microservices/microservices-architecture/microservices-vs-monolith)
### [Amazon](https://aws.amazon.com/fr/compare/the-difference-between-monolithic-and-microservices-architecture/)
### [F5](https://www.f5.com/fr_fr/glossary/monolithic-application#:~:text=Syst%C3%A8mes%20bancaires%20%E2%80%93%20De%20nombreux%20syst%C3%A8mes,qui%20les%20rend%20plus%20s%C3%BBrs.)

## Micro-serives


#### Exemple d'utilisation dans des projets connus

Netflix est une des premières grosses entreprises a être passée de monolithique à micro-services,
elle à même remporté le 2015 JAX Special Jury Award

## Event-driven

## Hexa