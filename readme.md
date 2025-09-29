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

- Base de code unique
- Généralement regroupant l'interface utilisateur, la base de données et l'application côté serveur
- Rapide et facile à concevoir
- Une seule unité à déployer
- S'exécute sur un seul serveur
- Scalabilité plus limitée parce qu'elle affecte un système entier
- Système moins flexible lorsqu'il s'agit d'ajouter des nouvelles fonctionnalités
- Pose un risque de point de défaillance unique qui entraînerait l'échec de toute l'application

|                    Avanatages                    |                   Incovénients                   |
|--------------------------------------------------|--------------------------------------------------|
|Pas besoin de traduire le code entre les services |Assez rigide : Difficile d'intégrer des nouvelles | 
|                                                  |technologies                                      |
|Plus facile à développer et à déployer            |Difficile à faire évoluer                         |
|Plus facile à tester, notamment en end-to-end     |Un changement peut modifier en cascade=>peu agile |
|Plus sécurisé, car moins de communication         |Obligé de tout rebuild et redéployer à chaque     |
|extérieure                                        |changement                                        |  
|Indépendante                                      |Une erreur peut tout arrêter, même si elle est    |
|                                                  |localisée                                         |
|Performante                                       |Nécessite une équipe bien organiqée               |

### Définition

L'architecture monolithique utilise une base de code unique pour plusieurs fonctions métiers,
chaque service sont interdépendants, ce qui implique que la moindre modification peut avoir des répercussions
sur le reste de l'application.

Modèle de développement logiciel utilisant une base de code unique qui centralise des composants interdépendants afin d'exécuter différentes fonctions métier.

Une architecture monolithique peut être envisageable voire nécessaire dans des petits projets. Mais dès que le projet se complexifie, il peut être compliqué de maintenir.

### Exemples d'implémentations (schémas)

- Monolithe modulaire (ou diagramme de composants) : un seul système découpé en plusieurs modules, donc une séparation des couches existant tout de même sur une même base de code
- Diagramme de dépendances : structuration du code monolithe par fonctionnalité plutôt que par couche, limitant les interfaces

![monolithique.png](monolithique.png)

![Exemple d'architecture](https://substackcdn.com/image/fetch/$s_!E9pa!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F0ae8c7d0-6b29-4621-9ee0-5c4d023448bf_1600x1187.png)
Exemple d'architecture monolithique

### Exemples d'utilisation dans des projets connus

- GitLab est sur une architecture "Monorails", basée sur le framework "Ruby on Rails"
- Instagram Server est également un système monolithe fonctionnant sous Django
- CMS (Wordpress, Shopify, Prestashop)

### Sources

https://aws.amazon.com/fr/compare/the-difference-between-monolithic-and-microservices-architecture/

https://dev.to/adrianbailador/monolithic-architecture-in-net-33i2

https://medium.com/@AtefMADDOURI/architecture-microservice-vs-monolithique-8b019834ba35

https://about.gitlab.com/blog/why-were-sticking-with-ruby-on-rails/

https://handbook.gitlab.com/handbook/engineering/architecture/design-documents/modular_monolith/

https://instagram-engineering.com/static-analysis-at-scale-an-instagram-story-8f498ab71a0c
[Atlassian](https://www.atlassian.com/fr/microservices/microservices-architecture/microservices-vs-monolith)
[Amazon](https://aws.amazon.com/fr/compare/the-difference-between-monolithic-and-microservices-architecture/)
[F5](https://www.f5.com/fr_fr/glossary/monolithic-application#:~:text=Syst%C3%A8mes%20bancaires%20%E2%80%93%20De%20nombreux%20syst%C3%A8mes,qui%20les%20rend%20plus%20s%C3%BBrs.)
[IBM](https://www.ibm.com/think/topics/monolithic-architecture)
[vFunction](https://vfunction.com/blog/what-is-monolithic-application)

## Micro-serives


#### Exemple d'utilisation dans des projets connus

Netflix est une des premières grosses entreprises a être passée de monolithique à micro-services,
elle à même remporté le 2015 JAX Special Jury Award

## Event-driven

## Hexa