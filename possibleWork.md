Issue 1:

Create a MySQL table called `issue` that includes the following:
- pk (autonumber)
- contactName
- anonymous [Y/N]
- datetime
- subject
- emergency
- ghRepoName
- ghIssueNumber

Issue 2:

Create a MySQL table called `comment` that includes the following:
- pk (autonumber)
- issueFK (foreign key: the PK of the associated `issue` record)
- datetime
- body

When an issue is created, an associated `comment` record will also be created

Issue 3:

Create a MySQL table called `statusHistory` that includes the following:
- pk (autonumber)
- issueFK (foreign key: the PK of the associated `issue` record)
- datetime
- newStatus (Valid values are values of refStatus.statusCode)

This table is to record the history of status changes. When an `issue` is created, a `statusHistory` record is created with `newStatus` set to the minimum value of the `refStatus` table.

Issue 4:

Create a MySQL table called `refStatus` - which is a "reference" or lookup table - that includes the following:

statusCode | StatusLabel

10 | 'Request Received'

20 | 'Problem confirmed'

30 | 'Fix defined'

40 | 'Fix implemented'

50 | 'Fix confirmed'


Issue 5: 

Creation of the model:

  * `CustomerIssue` is the class structure and it will mirror the `issue` database table
    * Will have additional properties for `comments` and `status`
      * `comments` will be an array of all associated `comment` records from the DB
      * `status` is the value from the most recent `statusHistory` record
  
  * the `save()` method:
    * When an `issue` record is created, the Github API must create an issue with the appropriate label via the webhook
    
  * A new method: `sync()`
    * The webhook will activate the method
    * Reference the psuedocode for more info:
      * // Ignore webhook calls for GH Issues that are not Customer Issues
          if the GH Issue is not in the mysql `issue` table then 
	          stop

          // Record new comments on Customer Issues
          if there is a new GH Issue comment that is not in the mysql `comment` table then
          	if the commment contains a status label then
	          	if the label is invalid then
			          log it
			          stop
		          else
			          create a statusHistory record
	          add a record to the `comment` table`
            
Issue 6:

Create a web form that includes:
  - contactName
  - Emergency (yes or no)
  - Subject
  - Body
  - Submit button
