<div style="text-align: right;">
    <a href="https://github.com/DSD-ESDC-EDSC/dynamic-org-chart/blob/master/README.fr.md">Fr</a>
</div>

# _DOC - dynamic organization chart_
DOC is a web-based applicaiton users can interact with as an employee directory and interactive organization chart.

## Features 
DOC serves users a searchable directory of employees and business units. Powered by [Elasticsearch](https://www.elastic.co/), the tool is robust to spelling mistakes, allowing users to find employees and business units with ease.

Once users have found the employee or business unit they are searching for, they can instantly see where in the organization that employee or business unit resides. Additionally, users can explore the organization chart interactively, and then see all of the people who belong to a particular business unit.

## Open Data and Open Source
This project is built on top of the GEDS [dataset](https://open.canada.ca/data/en/dataset/8ec4a9df-b76b-4a67-8f93-cdbc2e040098) which is available under the [Canada Open Government License](https://open.canada.ca/en/open-government-licence-canada). DOC is built entirely using open source tools such as [React](https://reactjs.org), [d3](https://d3js.org), [Flask](https://palletsprojects.com/p/flask/) and [Elasticsearch](https://www.elastic.co/).
                          
## Want to reuse the project code?
No problem! This repository is open sourced under the [???-ENTER] license. While the project is organized around GEDS, multiple components could be repurposed for organizational charts in other organizations.

# High-level Architecture
This repository links together several repositories that are all part of the same project. The related repositories can be found below:

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

## d3 and react for the user interface
The front-end of DOC is built aroun d3, a javascript library for creating interactive data visualizations. The scripts that process the original GEDS data output organizational charts in a JSON format that can be consumed by d3. This visualization is embedded inside of a  React application.

## Elasticsearch and REST API
Elasticsearch, an open source search framework, is used to create a searchable index over employee names and organiational units. Additionally, a REST API is created using Flask to provide specific resources to the front-end application.
                  
## Updated
Every 24 hours, a python script downloads a csv file from [Canada's Open Data Portal](https://open.canada.ca/en/open-data), processes it to extract the Government of Canada's organization structure, and writes tables to a SQL database. Since all application data are extracted from a regularly updated source, there is no maintenance work required to keep reference data up to date.
