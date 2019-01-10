# Log Analysis Project
This is a project for Udacity's [Full Stack Web Developer Nanodegree](https://www.udacity.com/course/full-stack-web-developer-nanodegree--nd004)
## Project Description:
Your task is to create a reporting tool that prints out reports (in plain text)
based on the data in the database. This reporting tool is a Python program
using the psycopg2 module to connect to the database.
### Questions to Answer:
1. **What are the most popular three articles of all time?** Which articles have been
accessed the most? Present this information as a sorted list with the most popular
article at the top.
1. **Who are the most popular article authors of all time?** That is, when you sum up
all of the articles each author has written, which authors get the most page views?
Present this as a sorted list with the most popular author at the top.
1. **On which days did more than 1% of requests lead to errors?**  The log table
includes a column status that indicates the HTTP status code that the news site sent
to the user's browser.

## Setup for Project:
This project is run in a virutal machine created using Vagrant so there are a few steps
to get set up:
#### Installing the dependencies and setting up the files:
1. Install [Vagrant](https://www.vagrantup.com/)
1. Install [VirtualBox](https://www.virtualbox.org/)
1. Download the vagrant setup files from [Udacity's Github](https://github.com/udacity/fullstack-nanodegree-vm)
These files configure the virtual machine and install all the tools needed to run this project.
1. Download the database setup: [data](https://d17h27t6h515a5.cloudfront.net/topher/2016/August/57b5f748_newsdata/newsdata.zip)
1. Unzip the data to get the newsdata.sql file.
1. Put the newsdata.sql file into the vagrant directory
1. Download this project: [log analysis]()
1. Upzip as needed and copy all files into the vagrant directory into a folder called log_analysis
#### Start the Virtual Machine:
1. Open Terminal and navigate to the project folders we setup above.
1. cd into the vagrant directory
1. Run ``` vagrant up ``` to build the VM for the first time.
1. Once it is built, run ``` vagrant ssh ``` to connect.
1. cd into the correct project directory: ``` cd /vagrant/log_analysis ```
#### Load the data into the database:
1. Load the data using the following command: ``` psql -d news -f newsdata.sql ```
1. *Note:* Checkout Udacity's [FAQ](https://classroom.udacity.com/nanodegrees/nd004/parts/8d3e23e1-9ab6-47eb-b4f3-d5dc7ef27bf0/modules/bc51d967-cb21-46f4-90ea-caf73439dc59/lessons/262a84d7-86dc-487d-98f9-648aa7ca5a0f/concepts/a9cf98c8-0325-4c68-b972-58d5957f1a91)
page if you are running into any errors here.


## Run The Project
1. You should already have vagrant up and be connected to it.
1. If you aren't already, cd into the correct project directory: ``` cd /vagrant/log_analysis ```
1. Run ``` python log_analysis.py ```

Generating this information will take several seconds, but will now start loading.

## Expected Output:
    Calculating Results...
    TOP THREE ARTICLES BY PAGE VIEWS:
        (1) "Candidate is jerk, alleges rival" -- 338647 views
        (2) "Bears love berries, alleges bear" -- 253801 views
        (3) "Bad things gone, say good people" -- 170098 views
    TOP THREE AUTHORS BY VIEWS:
        (1) Ursula La Multa -- 507594 views
        (2) Rudolf von Treppenwitz -- 423457 views
        (3) Anonymous Contributor -- 170098 views
    DAYS WITH MORE THAN 1% ERRORS:
        July 17, 2016 -- 2.3% errors
