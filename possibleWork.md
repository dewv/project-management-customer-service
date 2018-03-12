## Possible issues to work on ##


Create database to capture specified entries

#### HTML Form (Views)
  - Needs to have place for contact name
  - Needs to pull the date from server
  - //Drop-down list for different 'flags'
    * Bug
    * Idea/Suggestion
    * [Need name for service interruptions]//
  - Text box for problem/suggestion


#### UI (Views)
  - Separate HTML webpage
  - Read from databse and display neatly
  - Ability to sort 'requests'


#### Connect Database to Github Issues (Controller)
  - Needs research 

#### Create Database and Tables (Model)
  - Create databse with MySQL
  - Create two tables
  - ##### Table 1:
    - Name: issue
    - pk (autonumber)
    - contactName
    - anonymous [Y/N]
    - datetime [autocapture]
    - subject
    - description
    - emergency
    - ghRepoName
    - ghIssueNumber
  
  
  - ##### Table 2:
    - Name: comment
    - pk (autonumber?)
    - issueFK
    - datetime [autocapture]
    - body
    - newStatus [default: Null]
  
  
