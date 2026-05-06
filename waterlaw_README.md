# 2026 Startup Water Law

## About: 
DataLab and the UC Davis Center for Watershed Sciences are collaborating on a project  to compile environmental flow requirements for the state’s waterways, drawing on  historical legal pdfs. The project requires web scraping publicly available websites to  gather the historical pdfs, recognizing the text in those pdfs, normalizing the text, creating  a searchable database, and developing a metadata protocol for future use of the  documents.


Maintainer:  
Carl Stahmer, UC Davis DataLab, cstahmer@ucdavis.edu

Contributors:   
PI – Karrigan Bork, UC Davis School of Law, ksbork@ucdavis.edu  
PI – Sarah Yarnell, Center for Watershed Sciences, smyarnell@ucdavis.edu   
PI – Natalie R Merline, Postdoc, nmerline@ucdavis.edu 

Junior Data Scientist:   
Joyce Kim, UC Davis College of Letters & Science, joyki@ucdavis.edu  
Natalia Rostas, UC Davis College of Letters & Science, narostas@ucdavis.edu  
Andrew Jower, UC Davis College of Letters & Science, aljower@ucdavis.edu  
Sabrina Cheung, UC Davis College of Letters & Science, sabcheung@ucdavis.edu  
Nea Le, UC Davis College of Letters & Science, ngtle@ucdavis.edu


Date of data collection: Pre 1973 - 2026

Geographic location of data collection: Water bodies across California 

Information about funding sources that supported the collection of the data: California Department of Fish and Wildlife


## SHARING/ACCESS INFORMATION 

### Licenses/restrictions: 
The scraped pdf’s are public records from the state water resources control board, our dataset and its metadata are intended for research purposes.

### Citation: 


## DATA & FILE OVERVIEW

File List: 
<We have a repository called  sts_startup_water_law which we use in GitHub, as well as a shared google drive with the same name, used for storing all our data. The shared google drive allows each team member to have access to data and documents scraped and ocr’d by others, while the code resulting in these files is in github.>

#### [R]: [All code which we have worked on is stored in this folder in github.]
+ [issue_14_webscrape.R, issue_7_webscrape.R, issue_16_water_roghts_decisions_scraper.R, judge_script_R, judgedeterm.R, water_quality_certs_scrape.R]: [each file contains code to scrape pdfs on each of the websites]

+ [water_quality_certs_ocr.R, division_decisions_ocr.R]:  [These files contain code to OCR the webscraped pdf’s which include texts in the form of images]

#### [docs]: [texts that we want to include in github]
+ [team_agreenment.md]:  [The purpose of our team agreement is to have a written down guide of the norms and expectations that we set in the beginning of the project as a team. It has all of our signatures, expectations and roles.]

#### [Shared google drive: 2026_startup_water_law]
This shared google drive where we store all the resulting documents from our code.

#### [2026_startup_water_law]/[data]/[The data folder contains 6 folders, one for each website which we scraped. Each website has a set of 3 folders within, differentiating between:]

+ [data]/[scraped_pdf]: [This folder is the place to store all of the pdf’s we scraped from each of the websites, this contains all of the original copies before any changes.]

+ [data]/[extracted_text]: [All of the text files created before using ocr. This includes what was extracted from the pdfs as well as the empty files, as some of the pdf’s are images of text.]

+ [data]/[extracted_data]: [This folder is the place for all csv files containing coordinates of the location of each word. This is useful for the pdf’s containing images, as the text was unable to be extracted without OCR(optical character recognition). 
	
#### [2026_startup_water_law]/[docs]:[This folder is for storing text files with a lot of the initial information, such as the links to the websites which needed to be scraped.]

+ [2026_startup_water_law]/[docs]/[original_proposal]: [Various files including the goals of this project.]
+ [collected_CV’s.pdf]: [This file contains information about each of the PI’s backgrounds.] 
+ [DataLab project overview]: [The narrative proposal and brief description can be found here.]
+ [image1]/[image2]/[image3]: [images of different creeks.]

#### [2026_startup_water_law]/[figures]: [This folder is empty for now, but any visualizations we make throughout will be saved here.]

Relationship between files: 
To understand this project, I recommend starting in the google drive and reading through the project proposal in the docs folder to understand the goals of our work. Then, I would go over to github and look in our R folder for files starting with an issue name, these scripts pull pdfs from each website. Once the pdf’s are collected, the initial text extraction is completed and saved into the exctacted_text folders in our google drive. Since some of the pdf’s consist of images, they needed to be ocr’d. The scripts are in github, each script ending in ocr.R. They read the pdfs and return csv files with coordinate data, as well as the extracted texts which are saved in our shared google drive. 


## METHODOLOGICAL INFORMATION:

### Data Collection: 

To compile a comprehensive collection of local water regulations and legal frameworks, our team utilized R scripts to automate the scraping process of foundational legal documents from the California State Water Resources Control Board website, targeting specific categories such as Water Right Decisions, Water Right Orders, Water Rights Judgments/Determinations, Division of Water Rights Decisions, Water Quality Orders, and Water Quality Certification – FERC or Diversion. 

To implement this, we manually inspected each website's unique structure using browser developer tools to identify the specific HTML paths and CSS selectors. These unique paths allowed us to programmatically target and download the relevant legal document PDFs across the California Water Board website. 

This automated process retrieved thousands of PDF documents across varying jurisdictions and timelines and served as the raw data for subsequent OCR (Optical Character Recognition) and text analysis in order to develop software for legal research.


### Data Processing: 

The primary goal of the data processing phase was to transform raw PDF documents into structured text strings and coordinate data. Our raw data consisted of files of varying quality, ranging from modern searchable digital PDFs to older image based scans. Due to these differences, we implemented a conditional processing workflow:
+ **Digital PDFS:** For documents with a preexisting text layer, we used the pdftools library in R to directly extract text and spatial coordinates. 
+ **Image Based Scans:** To handle flattened images where text was not accessible, we utilized the tesseract library to perform OCR. This process takes images of each page to reconstruct the text. 
+ **Low Quality and “Bad” scans:** Can add method for processing bad pdfs (Nea’s Task)
By capturing both the text and coordinates, this extracted data was then processed using NLP software to identify, extract and categorize named entities. This allows our team to transform the unstructured text into a searchable repository that is accessible to future researchers. 

### Data Analysis: 

As of April 29th we have not yet hit the analysis phase of the project. 

### Software: 

To run the scraping and OCR scripts associated with this project, the following software environment and R packages are required:

Primary Software: 
+ [R (Version 4.0 or higher)](https://cran.r-project.org/): The core programming language used for data processing.
+ [RStudio](https://posit.co/download/rstudio-desktop/): The recommended Integrated Development Environment (IDE) for running the .R scripts.

Required R Packages: 
+ [tesseract](https://cran.r-project.org/web/packages/tesseract/vignettes/intro.html): OCR for image based PDFs.
+ [pdftools](https://cran.r-project.org/web/packages/pdftools/pdftools.pdf): Extracting text and metadata from digital PDFs.
+ [rvest](https://cran.r-project.org/web/packages/rvest/rvest.pdf): Webscraping of the Water Board sites.
+ [dplyr](https://cran.r-project.org/web/packages/dplyr/dplyr.pdf): Data manipulation and cleaning of extracted text.
+ [httr](https://cran.r-project.org/web/packages/httr/httr.pdf): Tool for handling HTTP requests.
+ [stringr](https://stringr.tidyverse.org/): Used for pattern matching and cleaning of text.
+ [purrr](https://cran.r-project.org/web/packages/purrr/purrr.pdf): Assist with functional programming.
+ [hunspel](https://cran.r-project.org/web/packages/hunspell/index.html): identifies miss spelled words
+ [spacyr](https://cran.r-project.org/web/packages/spacyr/vignettes/using_spacyr.html): NLP library that helps parcels text into parts of speech. This is used for entity recognition.

