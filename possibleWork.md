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
  - Submit button
  - If successfully sent, give feedback to sender ("Request Received")
  - Submitting the form:
    - Creates record in `issue` table and record in `comment` table
    - Creates Github issue(?)


#### UI (Views)
  - Separate HTML webpage
  - Read from databse and display neatly
  - Ability to sort 'requests'
  - Non-staff users can see only their requests
  - Staff users can see all requests


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
  
#### Github Issue
  - Body should include a link to (server)/customerIssue/:id/edit, where :id is pk of issue table record.
  
#### Comments
  - Users can create comments
  - Staff members(?) can also change the status value of the issue/request
    - Status values must be an immediate successor or predecessor
  - For REST API, this is an edit to the body of the issue in Github
