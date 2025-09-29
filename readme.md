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
- Si plus de ressources doivent être allouées, c'est tout le système qui prend les ressources => On passe très vite dans du gaspillage de ressources
- Limite l'introduction de nouvelles fonnctionnalités

|                    Avantages                    |                   Inconvénients                   |
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

De plus en plus d'applications passent d'une architecture Monolithique à une architecture Micro-serivice

### Définition

L'architecture monolithique utilise une base de code unique pour plusieurs fonctions métiers,
chaque service sont interdépendants, ce qui implique que la moindre modification peut avoir des répercussions sur le reste de l'application.
Modèle de développement logiciel utilisant une base de code unique qui centralise des composants interdépendants afin d'exécuter différentes fonctions métier.

Une architecture monolithique peut être envisageable voire nécessaire dans des petits projets. Mais dès que le projet se complexifie, il peut être compliqué de le maintenir.
Une architecture monolithique représente un système simple, développé sur une même base de code. Généralement constitué d'un front, d'un back et d'une BDD.

### Exemples d'implémentations (schémas)

- Monolithe modulaire (ou diagramme de composants) : un seul système découpé en plusieurs modules, donc une séparation des couches existant tout de même sur une même base de code
- Diagramme de dépendances : structuration du code monolithe par fonctionnalité plutôt que par couche, limitant les interfaces

![monolithique.png](monolithique.png)

![Exemple d'architecture](https://substackcdn.com/image/fetch/$s_!E9pa!,f_auto,q_auto:good,fl_progressive:steep/https%3A%2F%2Fsubstack-post-media.s3.amazonaws.com%2Fpublic%2Fimages%2F0ae8c7d0-6b29-4621-9ee0-5c4d023448bf_1600x1187.png)
Exemple d'architecture monolithique

![alt text](image.png)

### Exemples d'utilisation dans des projets connus

- GitLab est sur une architecture "Monorails", basée sur le framework "Ruby on Rails"
- Instagram Server est également un système monolithe fonctionnant sous Django
- CMS (Wordpress, Shopify, Prestashop)
- Les applications Legacy (les anciennes versions de Microsoft Office)

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

## Micro-services

### Caractéristiques
- Composants logiciels indépendants dotés de fonctionnalités autonomes qui communiquent entre eux à l'aide d'API.
- Nécessite davantage de planification et d'infrastructure au départ, mais devient plus facile à gérer et à maintenir dans la durée.
- Chaque microservice est une entité logicielle indépendante qui nécessite un déploiement conteneurisé individuel.
- Nécessite des outils de débogage avancés pour suivre l'échange de données entre plusieurs microservices.
- Modifications des microservices individuels sans affecter l'ensemble de l'application.
- Allocations des ressources individuellement, en fonction des besoins => Economie des coûts
- Promeut l'expertise par équipe
- Possibilité de changer de technologies selon les services
- Plus facile de mettre en place un CI/CD
- La communication par API peut exposer à des faiblesses de sécurité
- Peu être moins performante

- Architecture de plus en plus populaire

### Définition
- Une architecture micro-service représente des systèmes plus complexes où chaque fonctionnalités sont indépendantes.

### Exemples d'implémentations
![alt text](image-1.png)

### Cas d'utilisations
- Netflix (une des premières grosses entreprises a être passée de monolithique à micro-services, elle à même remporté le 2015 JAX Special Jury Award)
- Microsoft Office
- Amazon

### Sources
- AWS
- talend
- [IBM](https://www.ibm.com/think/topics/monolithic-architecture)
- [vFunction](https://vfunction.com/blog/what-is-monolithic-application)

## Event-driven

![Schéma simplifié de Event-Driven](https://www.scylladb.com/wp-content/uploads/Event-Driven-Architecture-diagram.png)
![Exemple plus complet](https://hazelcast.com/wp-content/uploads/2021/12/20_EventDrivenArchitecture.png)
![Exemple plus concret](https://media.geeksforgeeks.org/wp-content/uploads/20241024120522004425/event-driven-architecture-of-e-commerce-site.webp)*

### Caractéristiques
- Rend la maintenance plus facile
- Très réactif
- Scallable : l'ajout de consommateur ou d'émetteurs est simple et sans cascade
- Flexible
- Permet la communication asynchrone
- Peu devenir complexe avec plus d'événements
- Maintenir l'ordre des événement peut être compliqué
- Plus compliqué à débugger
- Peu causer d'important délai en fonction de l'ordre de traitement

### Définition
C'est un modèle de conception logicielle centré sur la production, la détection, la consommation et la réaction aux évenements. 

Cette architecture se compose principalement de 3 éléments : émetteurs, canal et consommateurs. Un émetteur va générer des évenements, le canal va les transmettre et un consommateur va réagir à l'évenement. Un consommateur suit un type d'événement et effectue une certaine logique en réponse.

### Exemples d'implémentations
- **Modèle de publication/abonnement**: Une fois qu'un événemment est émit, il est envoyé aux consommateurs immédiatement
- **Modèle de flux d'événements**: Les évenements sont inscrits dans un journal, et les consommateur peuvent lire tout le journal
### Cas d'utilisations
- Wix 
- Uber

### Sources

- [Bob le développeur](https://www.bob-le-developpeur.com/notions/event-driven-architecture)
- [Red Hat](https://www.redhat.com/fr/topics/integration/what-is-event-driven-architecture)
- [Microsoft](https://learn.microsoft.com/fr-fr/azure/architecture/guide/architecture-styles/event-driven)
- [Estuary](https://estuary.dev/blog/event-driven-architecture-examples)

## Hexa

### Caractéristiques

### Définition

### Exemples d'implémentations

### Cas d'utilisations

### Sources
