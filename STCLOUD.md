Mini Project 1 - Public Cloud Products and Services

More on enumeration of services. More concern

Delete the delete marker - restores the original file
Delete an uploaded - revert to earlier version


Good use cases of Amazon S3 - need to write once, read many times, spiky data access, large number of users and diverse amounts of content, growing data sets

Not ideal use cases - block storage requirements, frequently changing data, long term archival storage

Pay only for what you use including: 
1. GBs per month
2. Transfer OUT to other regions or the internet
3. PUT, COPY, POST, LIST  and GET  requests

You do NOT have to pay for Transfer IN to amazon S3 or transfer OUT to Amazon EC2 in the same region, or to CloudFront



Amazon S3 Standard - General Purpose
Amazon S3 Standard - Infrequent Access (IA)
Amazon S3 Intelligent Tiering
Amazong S3 One Zone-Infrequest Access

orage
Durability and availability
- Durable
	- high durability 99.11 9's of objects across multiple AZ
	- prone ba sa malfunction, sa corruption
	- If you store 10 million objects with S3, on average expect to incur a loss of a single object every 10k years
- Availabillity
	- Measures how readily available a service is
	- Varies depending on storage classes
	- S3 standard has 99.99% availability ~not available 53 minutes a year

## S3 Standard - General Purpose

- used for frequently accessed data
- 99.99 availability
- low latency and high throughput
- sustain 2 concurrent facility failures

use cases: big data analytics, mobile and gaming applicationns, content distribution.


## S3 Storage Classes - Infrequent Access

- for data less frequently accessed but requeires rapdi access when needed
- lower cost than S3 standard

use case: disaster recovery, in a data center failure, need may recovery / accessible data agad.


## S3 Glacier Storage Classes

- low cost storage meant for archiving / backup
- pricing: price for storage + pbject retrieval cost
- not rapid, ex scenario: wait up to 6 hours

- **Amazon S3 Glacier Instrant Retrieval**
- **Amazon S3 Glacier Flexible Retrieval**
- **Amazon S3 Glacier Deep Archive**



## S3 Intelligent-Tiering


- Small monthly monitoring and auto tiering fee
- Moves objects autopmatically between Access Tiers based on usage
- There are no retrieval costs


Why these are important?

- Parehas availability silang lahat besides standard IA,  one zone, glacier instant retrieval
- in terms of deployment of these buckets, standard has 3 availability zones usually, tapos kay IA, one zone lang.


## Lifecycle Rules


- Transition Actions - configure objects to transition to another storage class.




Budgets and Planning
Create a budget button
Zero spend template
That should be ok na, save changes

Monthly cost budget - depende sa budget, notify if nareach na yung allotted budget for the month

standard ia muna then after 30 days one, glacier for up to 365 days

