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

A 20-row sample of the cleaned data is in [`sample_cleaned.csv`](sample_cleaned.csv).

SCHEMA FOR COLLECTED DATASET:

version: version of Graph API which the changelog is referencing  
product: which of Meta's various APIs is reciving the change  
release_data: the release date of the changelog's changes  
section: which section the change is targeting/fixing/changing  
subsection: a specification of section of what specifically is being changed  
body: a description of the change  
change_type: the type of change (removal, modification, restriction)  

Important notes about this dataset:

Due to the way I scraped the changelogs, the data within the product column turned out to be very inconsistent. Because of this I will not be able to use this column in my final visualizations.

Groups and subsections sometimes have various NULL values where my changelog parser was unable to pick one up. This is due to each changelog being written in a slightly, or very different way to another. 

The change_types column is not scraped, but created by me based off of keywords contained within the change body. Terms "removed, will not be continued" flag a change as a "removal". I created term lists for each kind of change I am defining. The results are not completely accurate. This is due to the different wording of each changelog as well as having a limited set of terms which I search for in the body. These term lists are not a "catch-all" and some change types will be miscategorized or not catagorized as a result. 

Methods
--------

My first visualization aims to answer my question of how the shape of Meta's changelogs changed over the different versions.

This visualization can be found at [`change_types_by_version.png`](change_types_by_version.png).

From this visualization, the most notible change over time is from version 3.0 onwards. Version 3.0 of Meta's Graph API was released during the time of the massive Meta scandal in 2018. And from version 3.0 and onwards a visible increase in the number of restrictions introduced in each API version is shown. 

The methods for collecting, cleaning, and visualizing this data call all be found at [`ChangelogDataProject.ipynb`](ChangelogDataProject.ipynb).


Findings
---------

How to Reproduce
-----------------
