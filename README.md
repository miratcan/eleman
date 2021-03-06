<p align="center">
  <img src="assets/logo.png"><br />
  Fully dockerised job board app that uses airtable as database.
</p>

You can check our [youtube video](https://youtu.be/3lXs0bKfdMw) to understand what is this repo built for.

# Features

 * Eleman is ready to run with very few configurations.
 * Eleman has caching mechanism that copies Airtable data to local
   database to avoid hitting API limitations.
 * Eleman has built-in filtering mechanism that allows users to list jobs
   by tags, companies and search words.
 * Eleman Support for multiple fields like description, requirements,
   responsibilities etc.
 * Eleman has built-in Markdown support to show rich text formatted fields
   in Airtable.
 * Eleman Has simple and modest frontend tailored with tailwindcss framework.

# How to Use?

Check the document: [Eleman Docker Container Tutorial: How To Set Up & Configure](https://github.com/miratcan/eleman/wiki/Eleman-Docker-Container-Tutorial:-How-To-Set-Up-&-Configure)

# How to Contribute?
 
 I appreciate all kinds of help for this project. 
 and 
  
## How to build docker image?


    docker build -f docker/Dockerfile -t eleman .

## How to run development server?

Go to web app directory and create virtualenv with given commands:

    $ cd web/
    $ python3 -m venv venv

Install Python packages to that environment:

    $ source venv/bin/activate
    $ pip install -r requirements.txt
    
Run synch command, you must set AIRTABLE_BASE_ID and AIRTABLE_API_KEY
environment variables when running.

    $ AIRTABLE_BASE_ID=foo AIRTABLE_API_KEY=bar flask synch

After that you can run project:

    $ flask run

## How to Change Styles?

This project is using tailwindcss compiler to compile it's css file. You have
to install tailwindcss node package globally.

    npm install -g tailwindcss
    
After that you can make your changes on assets/web.css and compile it with
 given command:
 
     flask compile-css

> Note: Do not change web.css file on static folder directly. It's being
   generated from compiling process of assets/web.css  
