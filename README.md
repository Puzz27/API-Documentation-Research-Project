# API-Documentation-Research-Project
Final class project for INFO 4617
Micah S Crowe

This project aims to answer the question of how API documentation changes, the causes behind those changes, and what those changes mean for the APIs themselves.
I will answer this question through the use of static web scraping and API calls, including the CDX API from the Wayback Machine. 
The key stakeholder for this project will be Data Scientists, who rely on APIs and their documentation to conduct research. 
I am expecting to find big changes in documentation length after big internet events occur. I'm also expecting to see an increase in certain keywords after 2020.
I am curious about API documentation for a few major platforms, X, Reddit, and Meta's APIs will be my key focus. 

Data
-----
I am pulling the data for my first dataset from https://developers.facebook.com/documentation/development/graph-api/changelog.
This website contains all the information for the different changelogs within Meta's Graph API. I will be scraping the markdown versions of these changelogs which are hosted on the website.

Important information I will need from the changelog markdown files includes:
- Version and version timestamp
- Product to be changed (Graph API or Marketing API)
- The specific change mentioned within the changelog
- The section, subsection, and description of that change

I will be collecting changelogs from a sample of the API's avalible version history. 


Methods
--------


Findings
---------

How to Reproduce
-----------------
