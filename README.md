# ACER coding challenge for DevOps candidates
With this challenge we hope to learn how you approach technical tasks. You will be presented with two tasks. First, a scenario with an open response. Second a coding task.

Please read the entirety of this document carefully. Pay attention to the 'Requirements' sections, and most importantly "What we are looking for".

We are interested in seeing how you problem solve and design solutions. We understand that you may not be able to create a complete solution. If that is the case, please respond with what you would consider the core aspects of the solution. As you go through the requirements you might have questions. Our suggestion is to make assumptions and document them for the interview.

As part of ACER's recruitment process this challenge is confidential. This challenge is expressly shared by ACER to you for the purpose of assessing your job application. You will not share this challenge or your response to anyone else.

## The interview
We will be reviewing your response to the challenge prior to the interview.

During the interview we will discuss with you:
*	Your understanding of the requirements
*	Any modelling, assumptions or decision making that you made during your solution design
*	How you went about solving the requirements and your decisions about the solution architecture
*	We might add a new requirement to understand your ability to adapt to change
*	Considering anything omitted, how the solution could be improved given time

## What we are looking for
This coding challenge is designed to assess the following
*	How you understand scope and constraints
*	The quality of your code and solution design
*	How you respond to feedback
*	How you follow best practices
*	The maintainability and extensibility of the solution

## How to submit the coding challenge response back to ACER
*	Create a public repository in GitHub. Set the repository name to a UUID. (Generate a UUID here.|https://www.uuidgenerator.net/)
*	As you develop, make commits to this repository.
*	When complete, send the repository URL via email to the ACER staff who shared this exercise.

## Task 1 - Open Response
### Scenario
Your workplace provides its services through two custom-built PHP applications. Each application has its own MySQL database.

One application is public and customer facing. It has user accounts for end users. It has e-commerce functionality that relies on a third-party payment gateway.

The second application is for staff to perform administrative functions. It is only available on the company’s internal network. It has Single Sign-On through the local Active Directory.

The public application implements an API that is restricted to the administration application. The API allows the administration application to push updates, or to query for information.

The applications run on-premises as a load-balanced cluster of application servers and the two MySQL database servers.

### Requirements
Describe how you would approach designing a resilient and fault-tolerant AWS hosted infrastructure for these applications.

Please consider the following questions in your response.
1.	What AWS services would you use and why?
2.	How would you configure networking within that infrastructure while following the same or similar requirements for user access?
3.	List the security considerations and controls you would apply.

Organise the answers in a document titled 'Response' as part of the repository. Feel free to use images and diagrams to illustrate your solution.

## Task 2 - Coding
### Scenario
The software developers at your workplace require a consistent development environment to develop a LAMP stack application.

Your task involves creating a local development environment using Docker and Docker Compose.

### Requirements
1. A docker-compose.yaml file which defines 1 network and 3 services:
    *	"app" - Apache (or Nginx) + PHP
    *	"db" - A relational database, such as MySQL, MS SQL Server, etc
    *	"cache" - A memory cache service, such as Redis, Memcached, etc
2. The "app" Docker image should have related PHP extension bundles built in so that the application can connect to the relational database and memory cache services.
3. The above Docker images can be either built from Dockerfile or pulled from Docker hubs.
4. There should be volumes defined for each Docker image so that configuration files (such as http.conf and php.ini) and data files (such as mysql/data) can be organised outside the Docker containers.
5. A shell or Python script server.sh (or server.py) should be provided to:
    *	build / initialise the Docker images, and provision a default database
    *	start / stop / restart all docker containers
6. A "readme.md" file to provide the necessary information for the developers to quickly start their work. The information may include but not be limited to:
    *	how to use the script
    *	database connection information
    *	memory cache connection information
7. The solution files should be organised in a logical folder structure. The final folder structure may look like the following:
    ```
    /
    |--docker
    |  |--app               // "app" image resources, such as Dockerfile, *.conf, *.ini, etc
    |  |--db                // database image resoures
    |  |--cache             // memory cache image resources
    |--docker-compose.yml
    |--readme.md
    |--response.docx        // a Word doc with the response to the open response task
    |--server.sh            // or server.py
    |--src                  // PHP src folder, should be mapped to "/usr/local/www/src"
    ```
