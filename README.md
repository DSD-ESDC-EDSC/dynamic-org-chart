<div style="text-align: right;">
    <a href="https://github.com/DSD-ESDC-EDSC/dynamic-org-chart/blob/master/README.fr.md">Fr</a>
</div>

# _Dynamic Organizational Chart (DOC)_


## Project Overview

The Dynamic Organizational Chart (DOC) provides users the ability to search derived org charts for many Government of Canada departments and is executed as an open project by the Data Science Division within the Chief Data Office of Employment and Social Development Canada (ESDC). It is built using the same dataset that underpins the [Government Electronic Directory Services (GEDS)](https://open.canada.ca/data/en/dataset/8ec4a9df-b76b-4a67-8f93-cdbc2e040098), which is updated every 24 hours and made available on the [Canada Open Data Portal](https://open.canada.ca/en/open-data) under the Government of Canada's [Open Government License](https://open.canada.ca/en/open-government-licence-canada). DOC consists of two major components:

1. Several programs that download and process the open GEDS dataset every 24 hours into a hierarchical format that can be used to link employees to organizational units and vise versa.
2. A web application that, using the processed GEDS data, allows users to dynamically navigate the derived org charts as well as search the directory of business units and employees. The application makes it possible to cross reference these two information sources; users can search for employees/business units and see where they are on an org chart, or they can navigate the org chart and see which employees belong to a given business unit.

DOC, once fully realized, makes the task of finding who works where and on what dynamic, visual, and more efficient.

## History

DOC began as an offshoot of a related project aimed to improve the efficiency of new employee onboarding. During testing on the related project, many new employees pointed out that they couldn't find any clear solution to identify where other employees work and how different parts of the organization relate to eachother.

Based on this, the team wondered, what if there was an easy way for employees to search for other employees and business units and then automatically link this information to the organization's structure? Furthermore, what if we could build this product using open source software and open data in order to facilitate sharing, collaboration, and transparancy with all who might benefit from the end product or reuse parts of its code - the term Open Project is used to describe this thought. 

Motivated by these ideas, we built a prototype, tested it, and concluded that there was in fact some appetite for a new way to searth through and navigate the organization structure. Now, we have nearly completed the beta version of this product and are releasing all code used to create it.

## Motivation and Business Value
As we examined existing tools that allow the navigation of GEDS data, the team noticed a few key areas that could be improved upon. Listed below are the areas for improvement, and how DOC addresses them.

### 1. Typos and Spelling Mistakes

> __Current search tools do not appear to be robust to typos and spelling mistakes. Often times, a user may not know the exact spelling of a name or business unit, which makes it challenging to find teams and individuals.__

DOC leverages [Elasticsearch](https://www.elastic.co/), an open source search engine that can be used to index and search text documents. Rather than looking for exact matches on the user's search, Elasticsearch assigns a score to each document based on how relevant it is to the user's search.

This means that correct search results will appear even in the presence of small typos and spelling mistakes. A GIF further down in this document shows an example where the search term "__jean moulec__" correctly identifies "__Jean Le Moullec__" as the second result in the list - Jean Le Moullec is one of the members of the team working on DOC.

### 2. No Central and Openly Available Government Org Charts

> __Divisions and directorates have internal facing org charts and government departments sometimes have web pages outlining their  structure, however there does not appear to be an openly acccessible and navigatable central source for organizational charts.__

The web application for DOC features a dynamic, interative, and searchable organizational chart for the Canadian federal public service. The organization structure for the Canadian Federal Government is implicitly defined in the GEDS dataset, and the programs in DOC automatically extract this organization structure.

This means that, as long as the information in GEDS is kept up to date, organizational charts for the entire public service are available through DOC. Additionally, since the GEDS dataset is updated every 24 hours, the org charts in DOC can be effortless up to date.

### 3. No Fast Way to Cross-Reference Employees With Organizational Structure

> __There appears to be no straightforward way to cross-reference employee information with organizational information. Example use cases: a user wants to know who is the director that oversees a particular team or who to contact from a given team.__

DOC was initially designed to solve exactly this problem. With a single click, users can identify where an employee works, where a business unit is in the organization, and who the team members are in a particular business unit. With DOC, it is extremely fast to link these two sources of information to one another.

## Literature Review & Related Findings

There are existing tools that allow users to search federal employee directory data, primary of which being [GEDS](https://geds-sage.gc.ca/en/GEDS?pgid=002) itself. When clicking on an employee in GEDS, it is possible to see employee contact information as well as where in the organization that employee works. Based on our interactions with users, however, GEDS does not seem to be very robust to typos and spelling mistakes. GEDS appears to allow for several ways of formatting a name (e.g. "first-name last-name", "last-name, first-name", etc) but searches for exact matches (i.e. propper spelling). Another weakness with this tool is that it does not offer any way to visualize or dynamically interact with an organizational chart, despite the information being available in the underlying dataset (which cane be done in DOC).

External services that appear to use GEDS data to allow users to seach for federal employees are [goc411.ca](http://www.goc411.ca/) and [opengovca.com](https://opengovca.com). These present the resulting employee information slightly differently but, like GEDS, offer a limited set of functionality.

## The Tool & Features
The section below specifically highlights the features that DOC offers in more detail. Additionally, short GIFs are shown to illustrate how each feature works.

### Explore Derived Government Department Org Charts Interactively
The centrepiece of DOC is the interactive org chart for the Government of Canada. Users can select a government department from a dropdown menu, and their org chart (based on GEDS data) will appear on the screen instantly.

![Search Employees #1](gif/dropdown-click.gif)

Once an org chart is selected, users can click the nodes to expand or collapse business units. Grey nodes are business units that have business units underneath them, while white nodes do not contain business units underneath them. In this way, users are free to explore the organizational charts. The GIF below shows an example of a user exploring the org chart for Employment and Social Development Canada.

![Search Employees #2](gif/node-click.gif)

The org chart visualization supports pan and zoom functionality, so users can expand the view of the org chart well beyond their screen size, and still successfully navigate via the pan and zoom feature.

![Pan and Zoom](gif/pan-and-zoom.gif)

### Search Employees
Users can find employees with a free text search. Thanks to Elasticsearch, DOC is robust to many types of typos, spelling mistakes, as well as variations of name formatting. The GIF below illustrates the earlier mentioned example of a search for "__jean moulec__" correctly returning a result for "__Jean Le Moullec__", even though the search term contains several spelling mistakes.

![Search Employees #1](gif/name-search-1.gif)

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

## Open Source Software
The code in this project developed by the Data Science team, which is being redistributed under the open source MIT License, processes GEDS data into a hierarchical format that can be consumed by Javascript's d3 data visualization library. Additionally, the data from this csv can be used to populate several tables in a SQL database. Between these two data sources (and with the help of Elasticsearch to index employee names and organizational units), it is possible to link employees to organizational structure, and vice versa.

The user interface is a [React](https://reactjs.org) application that makes use of Javascript's [d3](https://d3js.org) data visualization library to create the interactive org chart. The REST API is built on Python's [Flask](https://palletsprojects.com/p/flask/) microframework. The project makes use of [Elasticsearch](https://www.elastic.co/) as an open source search framework, and has used [SQLite](https://www.sqlite.org/index.html) as an open source relational database for development purposes. As an object relational mapper (ORM), [SQLAlchemy](https://www.sqlalchemy.org/) was used, so migration to a production database is adaptable to any of the flavours of SQL databases that are supported by SQLAlchemy.

Many open source software and libraries we used to create DOC and must be ackowledged. These artificats, along with their corresponding open licenses (where one was found), are listed below. Users are advised to consult original sources for official information.

Attribution statements for other software and code artifacts used:
- [Elasticsearch Docker Image](https://www.elastic.co/guide/en/elasticsearch/reference/current/docker.html) - [Apache 2.0 License](https://www.apache.org/licenses/LICENSE-2.0)
- [SQLite](https://sqlite.org/copyright.html) - no license found
- [StackOverflow](https://stackoverflow.com/) - [Attribution-ShareAlike International Creative Commons License](https://creativecommons.org/licenses/by-sa/4.0/). Whenever significant snippets of code were borrowed directly from an answer, A link to the URL was posted in a docstring in the same file along with an acknowledgement giving credit to the original author.

Attribution Statements for Python and the libraries used:
* All licenses here were obtained using the [pip-licenses](https://pypi.org/project/pip-licenses/) package (which itself is licensed under the MIT license).
- [Python](https://docs.python.org/3/license.html) - Python Software License (PSF)
- [pandas](https://github.com/pandas-dev/pandas/blob/master/LICENSE) - BSD license
- [urllib3](https://urllib3.readthedocs.io/en/latest/) - MIT
- [SQLAlchemy](https://docs.sqlalchemy.org/en/13/copyright.html) - MIT
- [elasticsearch python client](https://elasticsearch-py.readthedocs.io/en/master/) - Apache 2.0 License
- [pip-licenses](https://pypi.org/project/pip-licenses/) - MIT
- [Flask](https://flask.palletsprojects.com/en/1.1.x/license/#source-license) - BSD-3-Clause
- [Flask-Cors](https://flask-cors.readthedocs.io/en/latest/) - MIT
- [Flask-JWT-Extended](https://flask-jwt-extended.readthedocs.io/en/stable/) - MIT
- [Flask-SQLAlchemy](https://flask-sqlalchemy.palletsprojects.com/en/2.x/license/) - BSD-3-Clause
- [flask-restx](https://flask-restx.readthedocs.io/en/latest/) - BSD-3-Clause

Attribution Statements (JavaScript and the libraries used in this project):
- [React](https://github.com/facebook/react/blob/master/LICENSE) - MIT
- [react-fontawesome](https://github.com/FortAwesome/react-fontawesome/blob/master/LICENSE.txt) - MIT
- [d3](https://d3js.org/) - BSD
- [react-bootstrap](https://github.com/react-bootstrap/react-bootstrap/blob/master/LICENSE) - MIT ([Bootstrap](https://getbootstrap.com/docs/4.0/about/license/)
- [react-dom](https://github.com/motorcycle/react-dom/blob/master/LICENSE.md) - MIT
- [react-router](https://github.com/ReactTraining/react-router/blob/master/LICENSE) - MIT
- [react-scripts](https://github.com/GraphCMS/react-scripts/blob/master/LICENSE) - MIT
- [react-tooltip](https://github.com/wwayne/react-tooltip/blob/master/LICENSE) - MIT
- [axios](https://github.com/axios/axios/blob/master/LICENSE) - MIT
- [resize-observer-polyfill](https://github.com/que-etc/resize-observer-polyfill/blob/master/LICENSE) - MIT
- [styled-components](https://github.com/styled-components/styled-components/blob/master/LICENSE) - MIT

## Open Data Sources
This entire project is built off of the [GEDS dataset](https://open.canada.ca/data/en/dataset/8ec4a9df-b76b-4a67-8f93-cdbc2e040098), which is made available under the Government of Canada's [Open Data License](https://open.canada.ca/en/open-government-licence-canada). Every 24 hours, this dataset is updated on the Government of Canada's [Open Data Portal](https://open.canada.ca/en/open-data) as a single csv file.
