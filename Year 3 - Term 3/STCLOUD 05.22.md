

Amazon S3 - Simple Storage Service

Object Storage

Amazon S3 is one of the main building blocks. Youre creating a pocket, and everything you put into it is an object.

Advertised as infinitely scaling storage

Many use Amazon S3 as a backbone

Durability - Gaano ka durable to handle data corruption
Availability - how much availability when disaster strikes. dapat available parin yung data
Event triggers - implement event. ie when add an object into pocket, or delete, it can configure to notify. 

## Sample Use Cases

Amazon S3 to host entire static websites. Amazon S3 provides a low cost highly available and highly scalable solution

Amazon S3 as a data store for computation or large scale analytics such as financial transasctions analaysis and trends. S3 can support these workloads because of horizontal scaling.

Amazon S3 is highly durable and scalable. Can be used as a backup and archival tool. You can move long term data in to Amazon Glacier through the use of lifecycle policies. 

- Backup and Stoage
- Disaster Recovery
- Archice
- Hybrid Cloud storage
- Application hosting
- Media hosting
- data lakes big data 
- software delivery
- static website -- gagawin ngayon

Nasdaq is a lead client of AWS kasi has stored 7 years of data into S3 Glacier
Sysco runs analytics on its data and gains business insights.


- store objects(files) in "buckets" (directories)
- Buckets must have a globally unique name (across all regions and accounts)
- Buckets are defined at region level
- S3 looks like a global service but buckets are created in a region
- Naming convention:
	- No uppercase
	- No Underscore but dash is ok
	- 3-63 char long
	- Not an IP
	- must start with lowercase letter or nuber
	- must NOT start with the prefix xn-
	- must NOT end with the suffix -s3alias

- Object vallues are the content of the body:
	- Max Object size is 5TB
	- If uploading more than 5 gb, must use "multi-part upload"
- metadata list of text key / value pairs - system or user metadata
- tags (unicode key / value pair up to 10)
- version iDb


- Bucket settings for Block Public Access

Versioning
You can version your files in Amazon S3
It is enabled at the bucket level
Same key overwriite will change the version

it is best practice to version your buckets
	protect against uninteded deletes
	easy roll back to previous version

Any file that is not versioned prior to enabling versioning will jadsodfj



