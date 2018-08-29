# HackYourFuture Website
Class 14 HYF Project

## README contents

1. Workflow / HYF to-do
2. User manual
>* DO NOT TOUCH
>* ANOMALIES
3. Technical details
>* Notes
>* Structure
4. Version control
5. Information regarding construction process.

## 1. Workflow/ HYF to-do
***NB:*** _"Automatic" means we have written various functions to enable the system to work given specific input_. :smiley:

Step | Description | Whose Action
---- | ----------- | :------------:
A. | A new class is advertised on HYF website/social media/other outlets. | HYF
B. | Candidate goes on website to apply on the [HYF website apply tab](http://hackyourfuture.net/apply). To apply, candidate has to fill in form with basic data - Name, address, educational background, etc. | Candidate
C. | After "Apply" is clicked, basic data is sent to backend. ***NB:*** _We have implemented functionality where a repeat submission is possible - we have assumed that the candidate knows his/her own email address, and will hold that constant. In the event that a duplicate application is submitted with the same email address, the other data is updated with the latest entry._ | Automatic
D. | Backend generates an email to be sent to the candidate, containing a token and instructions on submitting CV/Motivation Letter. | Automatic
E. | In the first upload page, candidate can choose to upload files for CV/Motivation, or write this in.  | Candidate
F. | After "Submit" is clicked, this is again sent to the backend.| Automatic
G. | HYF examines CV/Motivation Letter of candidates, assigning a score manually onto the Google spreadsheets. ***NB:*** _This is the first round where candidates can get screened out._ | HYF
H. | Successful candidates get sent an assignment (Khan Academy/Codepen) through email by HYF, also with a link to submit their assignments.   | HYF
I. | Candidate does and submits their assignments through the link. | Candidate
J. | HYF scores the assignments, and decides who to call. ***NB:*** _This is the second - and last - round where candidates can get screened out._| HYF
K. | HYF calls the candidates and makes a final decision. | HYF

## 2. User manual
***NB:*** _Before beginning, it is necessary to initialise the application._ 

Step | Description 
---- | -----------  
A. | Before opening each round of applications, it is necessary to configure/initialise the application.
B. | Before setting the website to work "live", check first that the relevant npm packages have been installed: In the command line interface, first change to the folder containing the website files. Then type `npm install`
C. | Next, type `npm run dev` to run the project.
D. | The user will then be prompted for the following:- client ID, client secret and document ID.
E. | First, click on the link which should look something like [this](https://developers.google.com/sheets/api/quickstart/nodejs).
F. | Then, click on the box _Enable The Google Sheets API_.
G. | _Either_ choose from an older project, or simply create a new project. 
H. | Make a note of the Client ID and Client Secret, and enter these into the command prompt when prompted.
I. | The backend is now "linked" to the Google spreadsheets. This is an example of a URL for a Google spreadsheet: ```https://docs.google.com/spreadsheets/d/1DgeDc8AyxMoMeceJ06CzwsocRakLItidl50uT1egEkI/edit#gid=0 ``` In this case, the spreadsheet ID is `1DgeDc8AyxMoMeceJ06CzwsocRakLItidl50uT1egEkI`.
J. | From here, you can choose either to use an existing google sheet (**do save your work before!**) or a new sheet.
K. | You may be prompted to enter a new token and/or to enter your email account, in which case simply follow the on-screen instructions.

_The notes below are based on the steps as enumerated in section **1** above._

**DO NOT TOUCH**: Generally speaking the backend user of the site does not need to touch any of the functions or code, other than possibly to change the dates in `content` > `en` > `apply` > `apply-dates.md`.

All the changes, after initialisation, should be handled on the Google sheets themselves. Particular attention is called to steps 1.G. and 1.J., where backend user's manual input is required.



## 3. Technical details.
***NB:*** _This is based on the steps as enumerated in section **2** above._

### Notes:

Section | Notes 
----- | -----------  
2.D | The scripts running this query live in `package.json`, entry "scripts". This generates a file called `google-sheet-config.json` in the `src` folder which is blank.
2.H-K | This populates the `google-sheet-config.json` file. The functions generating this are in `api` > `bin` > `create-dev-config`.This works via a resolve/reject function.


### Structure:

```
                        HOME ------ DONATE
                         |
        --------------------------------------------------------------
        |         |         |         |         |         |         |
      APPLY     TEACH    SUPPORT   CHAPTERS   ABOUT    CONTACT  WOMEN CODING TEASER
                                      |
                                       Map chapters
                                      |
                                      Chapter pages
                                      - Amsterdam
                                      - Brussels 
                                      - Copenhagen
                                      - Malmö 

```

## 4. Version control
This README was written by Jason Tan and is correct as of 2 September 2018.

This website was created by [Maartje/Mauro] on [] and was last worked on 2 September 2018 by Class 14:
* **A Team** (Fadi, Emad, Wael & Hadeel)
* **Big Voice Big Team** (Sarbast, Sobhi, Rashad & Murat)
* **Return 0** (Aya, Isaac & Jason)

## 5. Construction process

In week 1 of the project we had something called an event storm, which is to be found [here] ().

In week 2 of the project we proceeded
