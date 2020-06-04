<div style="text-align: right;">
    <a href="https://github.com/DSD-ESDC-EDSC/dynamic-org-chart/blob/master/README.fr.md">Fr</a>
</div>

# _DOC - dynamic organization chart_

## Employee Directory
The Dynamic Organization Chart (DOC) serves as a searchable directory of employees and business units. Powered by [Elasticsearch](https://www.elastic.co/), DOC is robust to spelling mistakes, allowing users to find employees and business units with ease.

## Interactive Organization Chart
Once users have found the employee or business unit they are searching for, they can instantly see where in the organization that employee or business unit resides. Additionally, users can explore the organization chart interactively, and then see all of the people who belong to a particular business unit.

## Open Data
This project is built on top of the GEDS [dataset](https://open.canada.ca/data/en/dataset/8ec4a9df-b76b-4a67-8f93-cdbc2e040098) which is available under the [Canada Open Government License](https://open.canada.ca/en/open-government-licence-canada).

## Open Source
This project is built entirely using open source tools such as [React](https://reactjs.org), [d3](https://d3js.org), [Flask](https://palletsprojects.com/p/flask/) and [Elasticsearch](https://www.elastic.co/).

## Web Based
DOC is entirely web-based. Once completed, users can interact with the tool by simply visiting a web page on their browser.
                            
## Built entirely on the GEDS dataset
Every 24 hours, a python script downloads a csv file from [Canada's Open Data Portal](https://open.canada.ca/en/open-data), processes it to extract the Government of Canada's organization structure, and writes tables to a SQL database. Since all application data are extracted from a regularly updated source, there is no maintenance work required to keep reference data up to date.

## Elasticsearch and REST API
Elasticsearch, an open source search framework, is used to create a searchable index over employee names and organiational units. Additionally, a REST API is created using Flask to provide specific resources to the front-end application.
                  
## d3 and react for the user interface
The front-end of DOC is built aroun d3, a javascript library for creating interactive data visualizations. The scripts that process the original GEDS data output organizational charts in a JSON format that can be consumed by d3. This visualization is embedded inside of a  React application.

                        </p>
                    </div>
                    <div class="col-1-of-2">
                        <img class="segment-image" src="svg/undraw-online-test.svg">
                    </div>
                </div>
            </section>
            <svg class="wave-top" viewBox="0 0 1439 147" version="1.1" xmlns="http://www.w3.org/2000/svg" xmlns:xlink="http://www.w3.org/1999/xlink">
                <g stroke="none" stroke-width="1" fill="none" fill-rule="evenodd">
                    <g transform="translate(-1.000000, -14.000000)" fill-rule="nonzero">
                        <g class="wave" fill="#eee">
                            <path d="M1440,84 C1383.555,64.3 1342.555,51.3 1317,45 C1259.5,30.824 1206.707,25.526 1169,22 C1129.711,18.326 1044.426,18.475 980,22 C954.25,23.409 922.25,26.742 884,32 C845.122,37.787 818.455,42.121 804,45 C776.833,50.41 728.136,61.77 713,65 C660.023,76.309 621.544,87.729 584,94 C517.525,105.104 484.525,106.438 429,108 C379.49,106.484 342.823,104.484 319,102 C278.571,97.783 231.737,88.736 205,84 C154.629,75.076 86.296,57.743 0,32 L0,0 L1440,0 L1440,84 Z"></path>
                        </g>
                        <g transform="translate(1.000000, 15.000000)" fill="#FFFFFF">
                            <g transform="translate(719.500000, 68.500000) rotate(-180.000000) translate(-719.500000, -68.500000) ">
                                <path d="M0,0 C90.7283404,0.927527913 147.912752,27.187927 291.910178,59.9119003 C387.908462,81.7278826 543.605069,89.334785 759,82.7326078 C469.336065,156.254352 216.336065,153.6679 0,74.9732496" opacity="0.100000001"></path>
                                <path d="M100,104.708498 C277.413333,72.2345949 426.147877,52.5246657 546.203633,45.5787101 C666.259389,38.6327546 810.524845,41.7979068 979,55.0741668 C931.069965,56.122511 810.303266,74.8455141 616.699903,111.243176 C423.096539,147.640838 250.863238,145.462612 100,104.708498 Z" opacity="0.100000001"></path>
                                <path d="M1046,51.6521276 C1130.83045,29.328812 1279.08318,17.607883 1439,40.1656806 L1439,120 C1271.17211,77.9435312 1140.17211,55.1609071 1046,51.6521276 Z" opacity="0.200000003"></path>
                            </g>
                        </g>
                    </g>
                </g>
            </svg>
            <section class="section-call-to-action">
                <div class="u-center-text u-margin-bottom-big">
                    <h2 class="heading-secondary">Interested in this project?</h2>
                </div>

                <div class="row">
                    <div class="col-1-of-2">
                        <h3 class="heading-tertiary u-margin-bottom-small">Are you a Canadian public servant?</h3>
                        <p class="paragraph">
                            Continue work on this project! Although a beta version of the application is almost complete, there is still a lot of work to do. 
                            Send an email, you can find our contact information on the 
                            <span class="text-link"><a href="https://github.com/Collinbrown95/dynamic-org-chart-master">Github repository</a></span>
                            for this project.
                        </p>
                    </div>
                    <div class="col-1-of-2">
                        <img class="segment-image" src="svg/undraw-our-solution.svg">
                    </div>
                </div>

                <div class="row u-conditional-reverse">
                    <div class="col-1-of-2">
                        <img class="segment-image" src="svg/undraw-proud-coder.svg">                    
                    </div>
                    <div class="col-1-of-2">
                        <h3 class="heading-tertiary u-margin-bottom-small">Want to reuse the project code?</h3>
                        <p class="paragraph">
                            No problem! This repository is open sourced under the (TODO: fill this in) license, so anyone can repurpose and reuse any of the code in this repository. 
                            While the project is organized around GEDS, multiple components could be repurposed for organizational charts in other organizations.
                        </p>
                    </div>
                </div>
            </section>
        </main>
        
        <!-- Tailwind modals -->
        
        <!--Modal 1-->
        <div id="modal-1" class="modal opacity-0 pointer-events-none fixed w-full h-full top-0 left-0 flex items-center justify-center">
            <!-- Modal overlay (background) (tailwind css) -->
            <div class="modal-overlay absolute w-full h-full bg-gray-900 opacity-50"></div>
            <!-- Modal container (tailwind css) -->
            <div class="modal-container bg-white w-11/12 rounded shadow-lg z-50">
                <!-- Modal Close button (tailwind css) -->
                <div class="modal-close absolute top-0 right-0 cursor-pointer flex flex-col items-center mt-4 mr-4 text-white text-md z-50">
                    <span class="text-md">&times; (Esc)</span>
                </div>

                <!-- Modal content (in-house styles) -->
                <div class="modal-content">
                    <!-- Modal Header -->
                    <div class="modal-content__title">
                        <h2 class="heading-secondary">Open Data</h2>
                    </div>
                    <div class="modal-content__x-button modal-close">&times;</div>
                    <!-- Modal Body -->
                    <div class="modal-content__header">
                        <h3 class="heading-tertiary">Building on top of Open Data</h3>
                    </div>
                    <div class="modal-content__main-text">
                        <p class="modal-content__main-text__p">
                            This entire project is built off of the 
                            <span class="text-link"><a href="https://open.canada.ca/data/en/dataset/8ec4a9df-b76b-4a67-8f93-cdbc2e040098" target="_blank">GEDS dataset</a></span>,
                            which is made available under the Government of Canada's 
                            <span class="text-link"><a href="https://open.canada.ca/en/open-government-licence-canada" target="_blank">Open Data License</a></span>.
                            Every 24 hours, this dataset is updated on the Government of Canada's
                            <span class="text-link"><a href="https://open.canada.ca/en/open-data" target="_blank">Open Data Portal</a></span>
                            as a single csv file.
                        </p>
                        <p class="modal-content__main-text__p">
                            The code in this project processes this data into a hierarchical format that can be consumed by Javascript's
                            <span class="text-link"><a href="https://d3js.org" target="_blank">d3</a></span>
                            data visualization library. 
                            Additionally, the data from this csv can be used to populate several tables in a SQL database.
                            Between these two data sources (and with the help of
                            <span class="text-link"><a href="https://www.elastic.co/" target="_blank">Elasticsearch</a></span>
                            to index employee names and organizational units), it is possible to link employees to organizational structure, and vice versa.

                        </p>
                    </div>
                    <div class="modal-content__img">
                        <img class="modal-content__img--img" src="svg/undraw-server-status.svg">
                    </div>        
                </div>
            </div>
        </div>

        <!-- Modal 2 -->
        <div id="modal-2" class="modal opacity-0 pointer-events-none fixed w-full h-full top-0 left-0 flex items-center justify-center">
            <!-- Modal overlay (background) (tailwind css) -->
            <div class="modal-overlay absolute w-full h-full bg-gray-900 opacity-50"></div>
            <!-- Modal container (tailwind css) -->
            <div class="modal-container bg-white w-11/12 rounded shadow-lg z-50">
                <!-- Modal Close button (tailwind css) -->
                <div class="modal-close absolute top-0 right-0 cursor-pointer flex flex-col items-center mt-4 mr-4 text-white text-md z-50">
                    <span class="text-md">&times; (Esc)</span>
                </div>

                <!-- Modal content (in-house styles) -->
                <div class="modal-content">
                    <!-- Modal Header -->
                    <div class="modal-content__title">
                        <h2 class="heading-secondary">Open Source</h2>
                    </div>
                    <div class="modal-content__x-button modal-close">&times;</div>
                    <!-- Modal Body -->
                    <div class="modal-content__header">
                        <h3 class="heading-tertiary">No strings attached.</h3>
                    </div>
                    <div class="modal-content__main-text">
                        <p class="modal-content__main-text__p">
                            This project was built entirely with open source software. The user interface is a 
                            <span class="text-link"><a href="https://reactjs.org" target="_blank">React</a></span> application
                            that makes use of Javascript's
                            <span class="text-link"><a href="https://d3js.org" target="_blank">d3</a></span>
                            data visualization library to create the interactive org chart.
                            The REST API is built on Python's 
                            <span class="text-link"><a href="https://palletsprojects.com/p/flask/" target="_blank">Flask</a></span>
                            microframework.
                            The project makes use of 
                            <span class="text-link"><a href="https://www.elastic.co/" target="_blank">Elasticsearch</a></span>
                            as an open source search framework, and 
                            <span class="text-link"><a href="https://www.postgresql.org" target="_blank">PostgreSQL</a></span> 
                            (probably) as an open source relational database.

                            </s>
                        </p>
                        <p class="modal-content__main-text__p">
                            This means that no licences, subscriptions, or payments of any kind are required to obtain or use this project.
                            The only cost involved is the cost of infrastructure required to host the application.
                        </p>
                    </div>
                    <div class="modal-content__img">
                        <img class="modal-content__img--img" src="svg/undraw-open-source.svg">
                    </div>    
                </div>
            </div>
        </div>

        <!-- Modal 3 -->
        <div id="modal-3" class="modal opacity-0 pointer-events-none fixed w-full h-full top-0 left-0 flex items-center justify-center">
            <!-- Modal overlay (background) (tailwind css) -->
            <div class="modal-overlay absolute w-full h-full bg-gray-900 opacity-50"></div>
            <!-- Modal container (tailwind css) -->
            <div class="modal-container bg-white w-11/12 rounded shadow-lg z-50">
                <!-- Modal Close button (tailwind css) -->
                <div class="modal-close absolute top-0 right-0 cursor-pointer flex flex-col items-center mt-4 mr-4 text-white text-md z-50">
                    <span class="text-md">&times; (Esc)</span>
                </div>

                <!-- Modal content (in-house styles) -->
                <div class="modal-content">
                    <!-- Modal Header -->
                    <div class="modal-content__title">
                        <h2 class="heading-secondary">Web based</h2>
                    </div>
                    <div class="modal-content__x-button modal-close">&times;</div>
                    <!-- Modal Body -->
                    <div class="modal-content__header">
                        <h3 class="heading-tertiary">Everything. In the browser.</h3>
                    </div>
                    <div class="modal-content__main-text">
                        <p class="modal-content__main-text__p">
                            This project takes the form of a web application, which means that it is consumed entirely through a browser.
                            This means that no installations are required, and nothing is dependent on a specific operating system.
                            The only thing you need is a modern browser!
                        </p>
                    </div>
                    <div class="modal-content__img">
                        <img class="modal-content__img--img" src="svg/undraw-static-website.svg">
                    </div>
                </div>
            </div>
        </div>

        <!-- Modal 4 -->
        <div id="modal-4" class="modal opacity-0 pointer-events-none fixed w-full h-full top-0 left-0 flex items-center justify-center">
            <!-- Modal overlay (background) (tailwind css) -->
            <div class="modal-overlay absolute w-full h-full bg-gray-900 opacity-50"></div>
            <!-- Modal container (tailwind css) -->
            <div class="modal-container bg-white w-11/12 rounded shadow-lg z-50">
                <!-- Modal Close button (tailwind css) -->
                <div class="modal-close absolute top-0 right-0 cursor-pointer flex flex-col items-center mt-4 mr-4 text-white text-md z-50">
                    <span class="text-md">&times; (Esc)</span>
                </div>

                <!-- Modal content (in-house styles) -->
                <div class="modal-content">
                    <!-- Modal Header -->
                    <div class="modal-content__title">
                        <h2 class="heading-secondary">Reusable</h2>
                    </div>
                    <div class="modal-content__x-button modal-close">&times;</div>
                    <!-- Modal Body -->
                    <div class="modal-content__header">
                        <h3 class="heading-tertiary">
                            Reduce. Reuse. Recycle.
                        </h3>
                    </div>
                    <div class="modal-content__main-text">
                        <p class="modal-content__main-text__p">
                            As we were developing this project, we wondered if anyone else in XXX was working on projects related to organizaitonal charts and employee directories.
                            In an effort to reduce the duplication of work related to organization charts and employee directories, we built this project with reusability in mind. 
                        </p>
                        <p class="modal-content__main-text__p">This project is broken into three Github repositories for:
                            <span class="text-link"><a href="https://github.com/Collinbrown95/react-hooks-d3" target="_blank">the user interface</a></span>, 
                            <span class="text-link"><a href="https://github.com/Collinbrown95/geds-api" target="_blank">the REST API</a></span>, and 
                            <span class="text-link"><a href="https://github.com/Collinbrown95/process-geds-data" target="_blank">the programs to assemble the data from GEDS</a></span>
                            used in this application. People are free to use code from any/all of these repositories for their own projects.</p>
                    </div>
                    <div class="modal-content__img">
                        <img class="modal-content__img--img" src="svg/undraw-product-iteration.svg">
                    </div>
                </div>
            </div>
        </div>

        <script>
            var openmodal = document.querySelectorAll('.modal-open')
            for (var i = 0; i < openmodal.length; i++) {
            openmodal[i].addEventListener('click', function(event){
                event.preventDefault()
                toggleModalByID(event.target.id);
            })
            }
            
            const overlay = document.querySelectorAll('.modal-overlay')
            console.log("overlays are: ", overlay)
            for (var i = 0; i < overlay.length; i++) {
                overlay[i].addEventListener('click', toggleModal);
            }
            var closemodal = document.querySelectorAll('.modal-close')
            for (var i = 0; i < closemodal.length; i++) {
            closemodal[i].addEventListener('click', toggleModal)
            }
            
            document.onkeydown = function(evt) {
            evt = evt || window.event
            var isEscape = false
            if ("key" in evt) {
                isEscape = (evt.key === "Escape" || evt.key === "Esc")
            } else {
                isEscape = (evt.keyCode === 27)
            }
            if (isEscape && document.body.classList.contains('modal-active')) {
                toggleModal()
            }
            };
            
            
            function toggleModal () {
            console.log("click")
            const body = document.querySelector('body')
            const modal = document.querySelector('.current-modal')
            console.log("general toggle modal; ", modal)
            modal.classList.toggle('opacity-0')
            modal.classList.toggle('pointer-events-none')
            body.classList.toggle('modal-active')
            modal.classList.remove('current-modal');
            }

            function toggleModalByID(i) {
                console.log('#modal-' + i)
                const body = document.querySelector('body');
                const modal = document.querySelector('#modal-' + i);
                modal.classList.toggle('opacity-0');
                modal.classList.toggle('pointer-events-none');
                body.classList.toggle('modal-active');
                modal.classList.add('current-modal');
            }

        </script>
    </body>
</html>


































# dynamic-org-chart
An interactive and searchable organization chart web application that is built using the Government of Canada Employee Contact Information (GEDS) dataset, which is made publicly available through the Government of Canada's Open Data portal.

This repository links together several repositories that are all part of the same project. The related repositories can be found below

- [User Interface (React and d3)](https://github.com/DSD-ESDC-EDSC/dynamic-org-chart-ui)
- [Back-end API (Flask) for data on employees and organizations](https://github.com/DSD-ESDC-EDSC/dynamic-org-chart-api)
- [Scheduled job (Python) to download and process GEDS data](https://github.com/DSD-ESDC-EDSC/dynamic-org-chart-scripts)

## High-level Architecture
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
