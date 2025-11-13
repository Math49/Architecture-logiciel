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

[devTo](https://dev.to/adrianbailador/monolithic-architecture-in-net-33i2)
[medium](https://medium.com/@AtefMADDOURI/architecture-microservice-vs-monolithique-8b019834ba35)
[gitlab](https://about.gitlab.com/blog/why-were-sticking-with-ruby-on-rails/)
[hadbook](https://handbook.gitlab.com/handbook/engineering/architecture/design-documents/modular_monolith/)
[instagram](https://instagram-engineering.com/static-analysis-at-scale-an-instagram-story-8f498ab71a0c)
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

### Caractéristiques
- Exécution de la couche métier à partir d'évènements
- Est constitué de 3 éléments : les producteurs d'évènements, les routeurs d'évènements et les consommateurs d'évènements
- Utilisé dans les applications micro-services
- Permet de coordonner les micro-services
- Très libre en therme de langage et plateforme d'exécution
- Un événement peut avoir comme source des entrées internes ou externes. Les événements peuvent être générés par un utilisateur (par exemple, clic de souris, frappe au clavier), une source externe (par exemple, une sortie de capteur) ou le système (par exemple, le chargement d'un programme).
- Adaptation aux changements, en prenant des décisions en temps réel

Modèle de publication/abonnement
Il s'agit d'une infrastructure de messagerie basée sur l'abonnement à un flux d'événements. Avec ce modèle, une fois qu'un événement s'est produit ou a été publié, il est envoyé aux abonnés qui doivent en être informés.

Modèle de flux d'événements
Avec un modèle de flux d'événements, les événements sont écrits dans un journal. Les consommateurs d'événements ne s'abonnent pas à un flux d'événements. Ils peuvent lire toute partie du flux et le rejoindre à tout moment.

### Définition
Un système orienté événements est conçu pour capturer, communiquer et traiter les événements entre des services dissociés. Les systèmes peuvent ainsi rester asynchrones tout en partageant des informations et en accomplissant des tâches. 

### Exemples d'implémentations
- Est utile pour de la surveillance de ressources
- 

### Cas d'utilisations
- Sotheby's a mis en place une architecture de type EDA pour son système de gestion des enchères

### Sources
- [aws](https://aws.amazon.com/fr/event-driven-architecture)
- [wikipedia](https://fr.wikipedia.org/wiki/Architecture_orientée_événements)
- [redhat](https://www.redhat.com/fr/topics/integration/what-is-event-driven-architecture)

## Hexa

### Caractéristiques
- Coeur métier isolé : la logique métier (domain + use cases) ne dépend pas de la BDD, du framework web, ni de l’UI. 
- Ports : ce sont des interfaces définies par le domaine pour interagir avec l’extérieur (ex. UserRepository, PaymentGateway, EmailSender). 
- Adapters : ce sont des implémentations concrètes des ports (ex. SqlUserRepository, MongoUserRepository, controller REST, CLI, etc.). 
- Symétrie entrée / sortie : UI, API, BDD, queue de messages, tests automatiques sont tous vus comme des “clients” branchés sur le même cœur via des ports. 
- Faible couplage & forte testabilité : tu peux tester le cœur métier avec des doubles (mocks/fakes) sans démarrer BDD ni serveur HTTP. 
- Échangeabilité des technos : tu peux remplacer une BDD, un système de paiement, une API externe en changeant seulement l’adapter. 
- Compatible DDD / Clean Architecture : très utilisé avec Domain-Driven Design et apparenté aux autres archis “domain-centric” (Onion, Clean). 
- Alternative aux couches classiques : ce n’est pas qu’un empilement UI → Service → Repository ; le cœur ne “voit” pas l’infrastructure. 

### Définition

L’architecture hexagonale (ou Ports & Adapters) est un style d’architecture qui organise ton application autour de son cœur métier (domain/core), et fait passer toutes les interactions externes (web, BDD, files, autres services…) par des ports (interfaces) et des adapters (implémentations techniques).
Objectif : avoir un cœur métier indépendant des technologies, facilement testable et remplaçable.

### Exemples d'implémentations

### Cas d'utilisations
- MMA
### Sources
https://alistair.cockburn.us/hexagonal-architecture
https://en.wikipedia.org/wiki/Hexagonal_architecture_(software)
https://blog.octo.com/architecture-hexagonale-trois-principes-et-un-exemple-dimplementation
https://docs.aws.amazon.com/prescriptive-guidance/latest/cloud-design-patterns/hexagonal-architecture.html
https://www.baeldung.com/hexagonal-architecture-ddd-spring
https://www.arhohuttunen.com/hexagonal-architecture-spring-boot/
https://scalastic.io/en/hexagonal-architecture/
https://codesoapbox.dev/ports-adapters-aka-hexagonal-architecture-explained/
https://miladezzat.medium.com/hexagonal-architecture-ports-and-adapters-pattern-5ad2421802ec
https://github.com/alexander-schranz/hexagonal-architecture-study
