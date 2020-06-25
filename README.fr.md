***PROJET - PAGE EN DÉVELOPPEMENT (TRADUCTION FRANÇAISE PRÉPARÉE AVEC [DeepL - version gratuite](https://www.deepl.com/translator))

<div style="text-align: right;">
    <a href="https://github.com/DSD-ESDC-EDSC/dynamic-org-chart/blob/master/README.md">English</a>
</div>

# Aperçu du projet

L'organigramme dynamique (DOC) offre aux utilisateurs la possibilité de rechercher des organigrammes dérivés pour de nombreux ministères du gouvernement du Canada. Il est exécuté en tant que projet ouvert par la Division des sciences des données au sein du Bureau de la dirigeante principale des données du ministère de l'Emploi et développement social Canada (EDSC), en collaboration avec l'équipe des Ressources humaines et de l'Innovation commerciale. Il est construit en utilisant le même ensemble de données que celui qui sous-tend les [Services d'annuaires gouvernementaux électroniques (SAGE)](https://ouvert.canada.ca/data/fr/dataset/8ec4a9df-b76b-4a67-8f93-cdbc2e040098), qui est mis à jour toutes les 24 heures et disponible sur le [Portail canadien de données ouvertes] (https://ouvert.canada.ca/fr/donnees-ouvertes) sous la [Licence de gouvernement ouvert](https://ouvert.canada.ca/fr/licence-du-gouvernement-ouvert-canada) du gouvernement du Canada. DOC se compose de deux éléments principaux :

1. Plusieurs programmes qui téléchargent et traitent l'ensemble des données SAGE ouvertes toutes les 24 heures dans un format hiérarchique qui peut être utilisé pour relier les employés aux unités organisationnelles et vice versa.
2. Une application web qui, en utilisant les données SAGE traitées, permet aux utilisateurs de naviguer dynamiquement dans les organigrammes dérivés ainsi que de faire des recherches dans le répertoire des unités commerciales et des employés. L'application permet de croiser ces deux sources d'information ; les utilisateurs peuvent rechercher des employés/unités commerciales et voir où ils se trouvent sur un organigramme, ou ils peuvent naviguer dans l'organigramme et voir quels employés appartiennent à une unité commerciale donnée.

DOC, une fois pleinement réalisé, rend la tâche de trouver qui travaille où et sur quoi, dynamique, visuelle et plus efficace.

## Histoire

Le DOC a commencé comme une ramification d'un projet ChatBot connexe visant à améliorer l'efficacité de l'embarquement des nouveaux employés. Lors des tests sur le ChatBot, de nombreux nouveaux employés ont fait remarquer qu'ils ne trouvaient pas de solution claire pour identifier où travaillent les autres employés et comment les différentes parties de l'organisation sont liées les unes aux autres. Sur la base de cette constatation, on a commencé à créer un moyen facile pour les fonctionnaires de rechercher d'autres employés et unités commerciales, puis de relier automatiquement ces informations à la structure de l'organisation. En outre, afin d'accroître la disponibilité et l'accès à l'outil, l'accent a été mis sur l'utilisation de logiciels et de données libres afin de faciliter le partage, la collaboration et la transparence avec tous ceux qui pourraient bénéficier du produit final ou réutiliser des parties de son code - le terme "projet ouvert" est utilisé pour décrire cette idée. 

Avec la construction d'un prototype, des tests avec des utilisateurs potentiels ont montré qu'il existe une demande pour une nouvelle façon de rechercher et de naviguer dans la structure de l'organisation. Le travail se concentre maintenant sur l'achèvement de la version bêta de DOC ainsi que sur la publication de l'ensemble du code.

## Motivation et valeur commerciale
Un examen des outils existants pour naviguer dans les données SAGE a révélé quelques domaines clés qui pourraient être améliorés. Les domaines à améliorer et la manière dont le DOC les aborde sont énumérés ci-dessous.

### 1. Typos and Spelling Mistakes

> __Les outils de recherche actuels ne semblent pas résister aux fautes de frappe et d'orthographe. Il arrive souvent qu'un utilisateur ne connaisse pas l'orthographe exacte d'un nom ou d'une unité commerciale, ce qui rend difficile la recherche d'équipes et d'individus.__

Le DOC exploite [Elasticsearch](https://www.elastic.co/), un moteur de recherche open source qui peut être utilisé pour indexer et rechercher des documents textuels. Plutôt que de rechercher des correspondances exactes sur la recherche de l'utilisateur, Elasticsearch attribue un score à chaque document en fonction de sa pertinence pour la recherche de l'utilisateur.

Cela signifie que des résultats de recherche corrects apparaîtront même en présence de petites fautes de frappe et d'orthographe. Un GIF plus bas dans ce document montre un exemple où le terme de recherche "__jean moulec__" identifie correctement "__Jean Le Moullec__" comme deuxième résultat dans la liste - Jean Le Moullec est l'un des membres de l'équipe travaillant sur DOC.

### 2. Pas d'organigramme gouvernemental central et ouvertement disponible

> __Les divisions et les directions ont des organigrammes internes et les ministères ont parfois des pages web décrivant leur structure, mais il ne semble pas y avoir de source centrale d'organigrammes ouvertement accessible et navigable.__

L'application web pour DOC présente un organigramme dynamique, interactif et interrogeable pour la fonction publique fédérale canadienne. La structure organisationnelle du gouvernement fédéral canadien est implicitement définie dans l'ensemble de données SAGE, et les programmes du DOC extraient automatiquement cette structure organisationnelle.

Cela signifie que, tant que les informations contenues dans SAGE sont tenues à jour, les organigrammes de l'ensemble de la fonction publique sont disponibles par l'intermédiaire du DOC. De plus, comme l'ensemble des données SAGE est mis à jour toutes les 24 heures, les organigrammes du DOC peuvent être mis à jour sans effort.

### 3. Pas de voie rapide pour croiser les employés avec la structure organisationnelle

> __Il ne semble pas y avoir de moyen simple de recouper les informations sur les employés avec les informations sur l'organisation. Exemple de cas d'utilisation : un utilisateur veut savoir qui est le directeur qui supervise une équipe particulière ou qui contacter à partir d'une équipe donnée.__

Le DOC a été initialement conçu pour résoudre exactement ce problème. D'un simple clic, les utilisateurs peuvent identifier où un employé travaille, où se trouve une unité commerciale dans l'organisation et qui sont les membres de l'équipe dans une unité commerciale particulière. Avec DOC, il est extrêmement rapide de relier ces deux sources d'information l'une à l'autre.

## Analyse documentaire et résultats connexes

Il existe des outils qui permettent aux utilisateurs de rechercher des données du répertoire des employés fédéraux, dont le principal est le [SAGE](https://geds-sage.gc.ca/fr/SAGE?pgid=002) lui-même. En cliquant sur un employé dans SAGE, il est possible de voir les coordonnées de l'employé ainsi que son lieu de travail au sein de l'organisation. Cependant, d'après nos interactions avec les utilisateurs, SAGE ne semble pas être très résistant aux fautes de frappe et d'orthographe. SAGE semble permettre plusieurs façons de formater un nom (par exemple, "prénom nom nom", "nom, prénom", etc.) mais recherche des correspondances exactes (c'est-à-dire une orthographe plus précise). Une autre faiblesse de cet outil est qu'il n'offre aucun moyen de visualiser ou d'interagir dynamiquement avec un organigramme, bien que les informations soient disponibles dans l'ensemble de données sous-jacent (ce qui peut être fait dans DOC).

Les services externes qui semblent utiliser les données SAGE pour permettre aux utilisateurs de rechercher des employés fédéraux sont [goc411.ca](http://www.goc411.ca/) et [opengovca.com](https://opengovca.com). Ces services présentent les informations sur les employés de manière légèrement différente mais, comme les SAGE, ils offrent un ensemble limité de fonctionnalités.

## L'outil et ses caractéristiques
La section ci-dessous met en évidence les caractéristiques que le DOC offre de manière plus détaillée. En outre, de courts GIF sont présentés pour illustrer le fonctionnement de chaque fonctionnalité.

### Explorez les organigrammes dérivés des ministères du gouvernement de manière interactive
La pièce maîtresse du DOC est l'organigramme interactif du gouvernement du Canada. Les utilisateurs peuvent sélectionner un ministère dans un menu déroulant, et leur organigramme (basé sur les données SAGE) apparaîtra instantanément à l'écran.

![Search Employees #1](gif/dropdown-click.gif)

Une fois qu'un organigramme est sélectionné, les utilisateurs peuvent cliquer sur les nœuds pour agrandir ou réduire les unités commerciales. Les nœuds gris sont des unités commerciales qui ont des unités commerciales en dessous d'elles, tandis que les nœuds blancs ne contiennent pas d'unités commerciales en dessous d'elles. De cette façon, les utilisateurs sont libres d'explorer les organigrammes. Le GIF ci-dessous montre un exemple d'utilisateur explorant l'organigramme pour Emploi et Développement social Canada.

![Search Employees #2](gif/node-click.gif)

La visualisation de l'organigramme prend en charge la fonctionnalité de panoramique et de zoom, de sorte que les utilisateurs peuvent étendre la vue de l'organigramme bien au-delà de leur taille d'écran, tout en naviguant avec succès grâce à la fonctionnalité de panoramique et de zoom.

![Pan and Zoom](gif/pan-and-zoom.gif)

### Recherche d'employés
Les utilisateurs peuvent trouver des employés grâce à une recherche en texte libre. Grâce à Elasticsearch, DOC est résistant à de nombreux types de fautes de frappe, d'orthographe, ainsi qu'aux variations de formatage des noms. Le GIF ci-dessous illustre l'exemple mentionné précédemment d'une recherche pour "__jean moulec__" renvoyant correctement un résultat pour "__Jean Le Moullec__", même si le terme recherché contient plusieurs fautes d'orthographe.

![Search Employees #1](gif/name-search-1.gif)


test test test


### Search Business Units 
This functionality is implemented in the back-end but not yet in the front-end. Once complete it will funciton in the same way as one searches for employees but for business units.

### See Who Works in a Given Business Unit 
It is possible to search with DOC in the opposite direction to what is mentioned above. Given a business unit, the user can see all of the people who work in that unit. Use cases for this include, for example, wanting to know who else works on an employee's team or wanting to find the manager of an employee. The GIF below illustrates, again using a member of the DOC development team, a search for "__brown, collin__" and correctly identifies his team members when clicking the "__See the team__" button.
![Search Employees #4](gif/name-search-4.gif)

# Technical Details
The next sections details the architecture, tech stack (open source software), and open data used in DOC.

## High-level Architecture
This repository links together several repositories that form that DOC Open Project. The related repositories can be found below:

- [User Interface (React and d3)](https://github.com/DSD-ESDC-EDSC/dynamic-org-chart-ui)
- [Back-end API (Flask) for data on employees and organizations](https://github.com/DSD-ESDC-EDSC/dynamic-org-chart-api)
- [Scheduled job (Python) to download and process GEDS data](https://github.com/DSD-ESDC-EDSC/dynamic-org-chart-scripts)

![architecture overview](https://g.gravizo.com/svg?digraph%20G%20%7B%0A%22GEDS%20data%22%20-%3E%20%22scheduled%20job%22%20%5Bcolor%3D%22blue%22%20label%3D%22downloads%22%5D%3B%0A%22scheduled%20job%22%20-%3E%20%22Elasticsearch%22%20%5Bcolor%3D%22red%22%20label%3D%22writes%20to%22%5D%3B%0A%22scheduled%20job%22%20-%3E%20%22SQL%20Database%22%20%5Bcolor%3D%22red%22%20label%3D%22writes%20to%22%5D%3B%0A%22Flask%20API%22%20-%3E%20%22SQL%20Database%22%20%5Blabel%3D%22reads%20from%22%5D%3B%0A%22Elasticsearch%22%20-%3E%20%22Front%20End%22%3B%0A%22Flask%20API%22%20-%3E%20%22Front%20End%22%3B%0A%22Front%20End%22%20-%3E%20%22Flask%20API%22%3B%0A%22Front%20End%22%20-%3E%20%22Elasticsearch%22%3B%0A%7D)

<!-- original graph -->
<!-- <img src='https://g.gravizo.com/svg?
digraph G {
"GEDS data" -> "scheduled job" [color="blue" label="downloads"];
"scheduled job" -> "Elasticsearch" [color="red" label="writes to"];
"scheduled job" -> "SQL Database" [color="red" label="writes to"];
"Flask API" -> "SQL Database" [label="reads from"];
"Elasticsearch" -> "Front End";
"Flask API" -> "Front End";
"Front End" -> "Flask API";
"Front End" -> "Elasticsearch";
}'/> -->

## Input Software
The code in this project developed by the Data Science team processes GEDS data into a hierarchical format that can be consumed by Javascript's d3 data visualization library. Additionally, the data from this csv can be used to populate several tables in a SQL database. Between these two data sources (and with the help of Elasticsearch to index employee names and organizational units), it is possible to link employees to organizational structure, and vice versa.

The user interface is a [React](https://reactjs.org) application that makes use of Javascript's [d3](https://d3js.org) data visualization library to create the interactive org chart. The REST API is built on Python's [Flask](https://palletsprojects.com/p/flask/) microframework. The project makes use of [Elasticsearch](https://www.elastic.co/) as an open source search framework, and has used [SQLite](https://www.sqlite.org/index.html) as an open source relational database for development purposes. As an object relational mapper (ORM), [SQLAlchemy](https://www.sqlalchemy.org/) was used, so migration to a production database is adaptable to any of the flavours of SQL databases that are supported by SQLAlchemy.

## Input Data Sources
This entire project is built off of **open data**, primarily the [GEDS dataset](https://open.canada.ca/data/en/dataset/8ec4a9df-b76b-4a67-8f93-cdbc2e040098), which is made available under the Government of Canada's open data license - [Open Government Licence - Canada](https://open.canada.ca/en/open-government-licence-canada). Every 24 hours, this dataset is updated on the Government of Canada's [Open Data Portal](https://open.canada.ca/en/open-data) as a single csv file.

# License
Unless otherwise noted, program source code of this project is covered under Crown Copyright, Government of Canada, and is distributed under the [MIT License](https://github.com/DSD-ESDC-EDSC/dynamic-org-chart/blob/master/LICENSE.md).

The Canada wordmark and related graphics associated with this distribution are protected under trademark law and copyright law. No permission is granted to use them outside the parameters of the Government of Canada's corporate identity program. For more information, see [Federal identity requirements](https://www.canada.ca/en/treasury-board-secretariat/topics/government-communications/federal-identity-requirements.html).

# Attribution
This project would not be possible without the availability and use of open source software. Acknowledgement and attribution to the open source tools used, along with their corresponding open licenses (where one was found), can be found in the [ATTRIBUTION.md](https://github.com/DSD-ESDC-EDSC/dynamic-org-chart/blob/master/ATTRIBUTION.md) file in this repository. Users are advised to consult original sources for official information, especially if they plan on re-distributing all or parts of these code artifacts.

# How to Contribute
Instructions for how to contribute can be found in the [CONTRIBUTING.md](https://github.com/DSD-ESDC-EDSC/dynamic-org-chart/blob/master/CONTRIBUTING.md) file.

