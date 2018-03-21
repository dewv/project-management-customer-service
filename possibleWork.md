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
