# AWS-Notes

This is listing my learning from [Cloud Computing Basics and Introduction to AWS Solution Architect](https://www.udemy.com/course/bulut-bilisim-temelleri-ve-aws-cozum-mimarligina-giris/).

## Introduction & Cloud History

1) The reason why Cloud Computing became popular is that Network capabilities have developed a lot.

2) 93% of companies use cloud computing in any way.

3) AWS is bigger than the collection of Microsoft Azure, Google Cloud, Alibaba cloud, IBM cloud and oracle cloud.

4) AWS Certificates:

![certificate](./images/001.png)

5) In order to install AWS CLI, activate a Python environment and install the following

```run.sh
pip install awscli
```

![client_vs_server](./images/002.png)

6) Virtualization software is installed on top of physical machine.

7) How to build a data center

    - Security, not allowinh everyone to enter
    - Keeping the temperature cold
    - UPS devices against short electricity cuts and generators against long electricity cuts.
    - Buy rack cabinets to place servers(physical machines)
    - Providing networking via ethernet cables.
    - Security cameras to secure data center

![data_center](./images/003.png)

8) Some companies decided to have a single data center rogether rather than multiple data centers. This concept is called as **colocation**. In this concepts, each company has different rack cabinets. This approach reduced the cost of air-conditioning&security dramatically but not didn't solve the capacity problem.

9) IaaS solved the problem of insfrasracture, capacity and data centers by intorucing selling Vm's for customer directly. The IaaS provider is responsible for all physical infrastructure. The renters are responsiblge for their VM's.

10) Cloud computing is not a product, it is a service.

11) On premises, IaaS, PaaS, SaaS

![comparison](./images/004.png)

12) AWS EC2(Elastic compute cloud) is an example of IaaS. AWS Elastic Beanstalk is an example of PaaS. AWS Workdocs(similar to Microsoft sharepoint) is an example of SaaS.

13) PaaS is a further step to IaaS. In PaaS, we are just managing data and application and other layers are managed by our providers. AWS Elastic Beanstalk is an example of PaaS. Heroku is an example of PaaS too.

14) In SaaS, everything is under the responsibility of our provider. We are just using it by paying. Gmail is an example of SaaS.

15) Pizza metaphore for On premises, IaaS, PaaS, SaaS

![pizza](./images/005.png)

16) Beta Release is carried out with customer. Beta version is launched and sent to customer first, then feedbacks are taken into consideration.

17) SaaS is predominant now in industry. SaaS is like renting a car rather than purchasing a car.

18) DevOps is a philasophy, not a method.

19) Docker, Jenkins, Ansible, Chef and Github actions are some softwares that are used in CI/DC processes.

20) Monolith applications are

    - hard to sustain
    - not flexible
    - hard to fix
    - having only one codebase
    - bulky

21) API is an explicitly defined communication management approach among different applications.

22) API Gateway is illustrated below. Common missions of API Gateway is direction, merging and protocol translation. Also, they are responsible for authentication, load balancing, monitoring. "One Api to rule them all".

![api_gateway](./images/006.png)

## AWS History

1) AWS was first created in 2002 and launced in 2006.

2) Some AWS Services year by year

![aws_services](./images/007.png)

3) AWS Official Sources:

    - [https://aws.amazon.com/new/](https://aws.amazon.com/new/)
    - [https://aws.amazon.com/blogs/aws/](https://aws.amazon.com/blogs/aws/)

4) AWS re:invent is a yearly conference held at late November & early December. It is the most transformative event in tech. It is in Las Vegas and more than 40k IT engineers are attending. Its price is around 1800 dollar.

5) There are more than 200 AWS services as of November 2022. Some AWS Services:

![aws_services](./images/008.png)

6) World undersea fiberoptic routes

![aws_services](./images/009.png)

7) AWS has many regions like North America or Central Europe. Each region has at least 2 Availability zones (AZ). Each AZ are connected to each other in the ame region.

8) In order to deliver static content better, CDN(Content Delivery Network) was introduced. AWS has a CDN service called CloudFront. There are 149 edge locations in AWS, which deliver static content.

9) [aws.amazon.com/free](https://aws.amazon.com/free/?all-free-tier.sort-by=item.additionalFields.SortRank&all-free-tier.sort-order=asc&awsf.Free%20Tier%20Types=*all&awsf.Free%20Tier%20Categories=*all) is a free website to learn AWS services without paying money.

![aws_free_services](./images/010.png)

10) We can manage AWS via GUI or CLI.

11) The oldest regions on AWS is Virginia & Ireland. There are some services that are available on one region, and not on another region. To view which region has which services, take a look at [here](https://aws.amazon.com/about-aws/global-infrastructure/regional-product-services/). Solution architexts use this information in building architectures.

12) We can assign tags to AWS services that we created. These tags are in the format of key:pair(Json file alike or Python dictionary alike). Then, we can list a resource group composed of different services with this tag.

13) It is good to know Account ID. It is shown under username -> Account tab. It is a 12-digit number. It is used in case of call center contact & ticket support etc.

14) IAM means identity and access management. IAM service prodives us with new created users. AWS doesn't want us to make operations as root. Therefore, we are required to create IAM users and make operations via these new users. IAM users can't access to billing pages or other administrative pages.

15) Cost Explorer is a tab in Account page. It enables us to view details of our costs.

16) Some Infrastructure as code tools are
    - Terraform
    - Ansible
    - Puppet
    - Chef

## Introduction to AWS Services

1) Compute is listing server services. 

    - EC2 is the most important service.
    - Lightsait is similar to EC2, but appropriate for test & dev enrionments and small businesses.
    - ECS is Elastic container service and it is a container orchestration tool.
    - EKS is Elastic Kubernetes service.
    - AWS Lambda is providing code execution without server management. You only pay the consumption.
    - AWS Batch: Automated batch processing.
    - Elastic Beanstalk: An orchestration service which orchestrates many AWS Serices like EC2, S3, Elastic Load Balancers. It is a PaaS service.


2) The 2 hot topics in the industry are Container & Serverless. AWS Lambda is a Serverless service. It reduces costs of developing applications.

3) Storage is listing storage-linked services.
    - S3: This is the service that booms Cloud Computing. It is storing the data irrespective of its source. S3 is object-base rather than blog-based. We can hold files whose sizes are between 0 KB to 5 TB.
    - EFS(Elastic File System): It can be thought as a flexible hard disc. Many computers can access to it simultaneously.
    - Glacier: Long-term & cheap & archiving service. Similar to S3.
    - Storage Gateway: Some firms use their own servers locally. owever, they want to keep their backups on the cloud in case of disaster recovery.

4) Database services are listed below.

    - RDS: Relational database services. It faciliates executing and scaling of databases(Amazon Aorora).
    - DynamoDB: Nonrelational database services.
    - ElastiCache: Providing completely managable Redis & Memcached. It is a cache memory service. Used in gaming.
    - Neptune: Appropriate for Graph DB's.
    - Redshift: It is a database in fact but specialized in merging different data from different sources. 10x faster than other data warehouses. THe reason why to use Redshift is that we don't want to consume the resources of our databases. Instead, we move the data to Redshift and query in Redshift.

5) Networking and Content Delivery

    - VPC: Virtual Private Cloud. It is a virtual network on the cloud. We can customize our network.
    - CloudFront: It is a CDN(Content Delivery Network) service.
    - Route53: It is a DNS(Domain Name Service). It is an alternative to GoDaddy. DNS runs on UDP 53 port and this is why it is named as Route53.
    - API Gateway: An API management tool bult in front of API.
    - Direct Connect: It is a cloud service faciliating the installation of deciated & private link between our local servers to AWS servers. It is a replacement for internet connection.

6) Migration

    - Migration Hub: A monitoring too for AWS migration operations.
    - Application Discovery: A service to discover applications on local servers before migration.
    - Database Migration Service: A migration service for databases. It supports homogeneous( example: Postgresql to Postgresql) & heterogeneous (MySQL to Amazon Aurora) migrations.
    - Server Migration Service: A service to move local servers to AWS servers.
    - Snowball: A migration tool to move Petabytes of data to AWS. It is a PHYSICAL device. AWS sends it to you. You put your data into this device in a encrypted way. You send it back to AWS. AWS restores services via this PHYSICAL device.

7) Management Tools are used in managing AWS Resources

    - Cloudwatch: A monitoring tool for RAM, CPU, disc, bandwith etc on servers. For example, if CPU limit exceeds 80 %(detected by Cloudwatch), then add a new server etc.
    - CloudTrail: A monitoring tool for all activities on AWS. Some activities are like who deleted S3 service, who increased the RAM of EC2 etc.
    - CloudFormation: A service suitable for repetitive task. For example, we create a cluster of virtual servers once a day. Then we are destroying them all. Instead of doing this manually, we are writing our instructions in a file(similar/equivalent to infrastructure as code solutions), then run them on CloudFormation.
    - Autoscaling: A service to automatically scale AWS resource in case of heavy load(CPU Bound > 80%).
    - Config: A monitoring tool for configuration settings. Configuration version of CloudTrail. It takes snapshots of current configuration settings.
    - Opsworks: A service version of Chef & Puppet in AWS world.
    - SystemCatalog: A service to restrict which IAM users can access to which service.
    - SystemsManager: A service providing us with managing all of our resources at the same time. For example, we want to upgrade OS's of our EC2 instances to Ubuntu Server 22.04 at the same time. It is possible with SystemsManager.
    - AWS Trusted Advisor: A service which suggests best practices for our existing services. For instance, there are 2 cores on our EC2 instance but our CPU doesn't exceed 30%. In this scenario, Trusted Advisor suggests us to reduce core number of our machine.
    - AWS Managed Services: A service listing 3rd party vendors of AWS. You can get support from these vendors. If we don't want to run our AWS infrastructure and want a 3rd party firm to manage it, these firms are ready on Managed Services

8) Security, Identity & Compliance

    - IAM: Identity and Access Management, managing accesses to AWS services and Resources. It is the heart of AWS.
    - Amazon Cognito: A service to faciliate log in activities via Google, Facebook, Amazon.
    - Secrets Manager: A service for hiding credentials(API keys, DB username passwords etc). You send a request to Secrets Manager API to use the info in your code.
    - Guard Duty: A security service monitoring all AWS services. It detectes anomally API calls etc via Machine Learning Algorithms.
    - Inspector: A security service detecting security bugs in our apps.
    - Macie: A service detecting sensitive data on S3. Detection is carried out through Machine Learning.
    - SSO - Single Sign On: Its logic is similar to 1password.
    - Certificate Manager: A service for SSL/ TLS certificates. Its logic is similar to let's encrypt.
    - CloudHSM - Hardware Security Module: An encrypting service for our data(not well understood)
    - AWS Active Directory.
    - WAF - Web Application Firewall: It protects our apps deployed on AWS from attacks like sql injection.
    - Shield: A serice protecting us from ddos attacks.
    - Artifact: A tool to obtain documents for auditing.

9) Application Integration

    - SQS (Single Queue Service): A message broker service, similar to RabbitMQ and Kafka. It is simple and con so comprehensive.
    - SNS: Simple Notification Service: One of the most used Amazon Services. It prompts alerts & notifications. For example, a pop-up appearing on our phone from an e-commerce app can come from this service. An alert generated by CloudWatch may come from this service.
    - SWF: Single Workflow Service. Similar to Apache airflow.
    - Step Functions: It is enabling us to run multiple AWS services consecutively in a **serverless** manner.
    - MQ Message Queue: Based on RabbitMQ, but more extensive compared to SQS. 

10) Analytics:

    - Athena: It is used to make SQL queries on S3. It is interactive and serverless. You pay as you use.
    - Elastic MapReduce: A tool to store big data. It is an alternative to Apache Hadoop.
    - CloudSearch: A tool to make search possible on our websites, supporting more than 30 languages
    - Elasticsearch: Similar to elastic search, read operations are fast, for example log analysis is an area that amazon elasticsearch service used.
    - Kinesis: A tool making real time analysis, used with IoT devices.
    - Quicksight: A BI tool, similar to PowerBI & tableau
    - AWS Data Pipeline: A service to transfer data between different services(S3, RDS, DynamoDB)
    - Glue: A tool for ETL

11) Customer Engagement:
    - SES (Simple Email Service):  An email sender. An alternative to Sendgrid. It is used in campaigns. If you also want to add a feature of sending emails to your app, SES might be a choice.
    - Amazon Connect: A call center service for small companies. Amazon uses this service in its Call Center Operations
    - Amazon Pinpoint: A service to send push messages(a discount by 20%, a new t-shirt appearing etc). It not only sends push messages, but also analyzes the data before sending push messages.

12) Mobile Services:
    - Mobile Hub: It isn't a service, it is an interface. It visualizes the services constituting the mobile app.
    - AppSync: A tool to syncronize offline apps. For instance, your connection was cut off. When you connect to internet, you should be able to view latest tweets on Twitter. This is what AppSync does.
    - DeviceFarm: A service to physically test our mobile app. Let's assume that you developed an android app and want to test it. There are many phone brands and each brand has different phone models. DeviceFarm service tests our app on different models of phones.

13) Desktop & App Streaming:

    - Workspaces: It is called VDI(virtual desktop). It creates a desktop machine(windows or linux etc) remotely and you are accessing it via RDP.
    - Appstream 2.0: It is making you desktop app(for instance, .exe extension file ) accessible through browsers. Other users are using/testing your app via their browsers.

14) Media Services:

    - Elastic Transcoder: It is making our videos watchable in different devices such as tablets, phones and pc's.
    - Kinesis Video Streams: Faciliating video streams.
    - Media Services: Video storages and streaming. If you want to create you own Youtube, it is the correct choice.

15) Business Productivity:
    - Alexa for business: A voice assistant.
    - Chime: An alternative to Microsoft Teams or WebEx or Zoom.
    - Workdocs: Similar to one drive for business or google drive.
    - Workmail: Similar to office 365 or gmail.

16) Developer Tools:

    - Cloud9: A web based IDE
    - Codecommit: An alternative to Github.
    - CodeBuild. An alternative to Jenkins. It is packaging the app.
    - Codepipeline: It i building up the pipeline.
    - CodeDeploy: It is deploying apps.
    - CodeStar: A visualization tool for all of these processes.
    - X-ray: Analyzing our app to debug.

![developer_tools](./images/011.png)

17) Machine Learning:
    - Sagemaker: A platform to develop, train and distribute ML models
    - Comprehend: A tool for NLP tasks such as text summarization, sentiment analysis, removing toxic words etc.
    - DeepLens: A Computer Vision service for video analysis.
    - Lex: A speech recognition(may also include text but I am not sure) tool. For example, you want to add a feature that recoginzes voice of your customers and brings what they want as results.
    - Polly: A text to speech tool. Some news websites is using this service to create voices from the articles of their authors.
    - Amazon Rekognition: A comprehensive computer vision service. It detects people and objects and inappropriate content etc. It is used by AmazonGo probably.
    - Translate: A translation service.

18) Internet of Things:

![developer_tools](./images/012.png)

19) AR & VR

    - Sumerian: 

20) Game Development:

    - Gamelift: A speciliazed service for gaming. It aims to reduce latency and wait time.

21) re-invent: 2018 Services:

    - Timestream: Cheap & Time series DB. Actually, it is a NoSQL solution.
    - Amazon Textract: An improvement to OCR. It extracts text and data from scanned papers.
    - Managed Blockchain: It creates blockchain.
    - Deepracer: A demo car for self-driving cars. Its size is smaller by 1/18 ratio.

22) Main Services on AWS:

    - Compute
    - Storage
    - Database
    - Networking and Content Delivery
    - Management & Governance
    - Security, Identity & Compliance

## AWS Services in Detail

### Budgets

1) We can create budgets and alerts linked to these budgets. If we don't want to pay more than 10 dollar to AWS per month, we can create a bucget and assign an alert to this budget. We can customize budgets for services(EC2 not exceeding 20 dollar per month etc)

### IAM

1) IAM is Identity and Access Management. It is the heart of AWS. IAM is independent from region.

2) IAM objects are
    - Users: Root user is the first user who creates the account. Further users are non-root users. Root user create other users and assign roles to them. Root user shouldnt be used after creating new IAM users.
    - Groups: Groups are objects that are composed of users. We can assign authorization to groups, therefore users are equipped with authorization.
    - Roles: Role is the authorization system of IAM. If we want our S3 service to be accessible by EC2, we should define a role. If we want another person to use the resources of our AWS account, we should create a role.
    Roles are composed of 2 components: who can use this role(assign to whom), the authorizations & what to do with the role. The second component is made with Policies.
    - Policies: Policy is a file which means who can accces to which service with which authorization. Then we can link the policy to a user or a group. Policy is in the format of JSON. Policies are in 2 ways: common templates generated by AWS or custom templated generated by us.

3) All of password management procedures like 2FA are made in IAM.

4) Non-root users(IAM Users) should access to AWS via the link https://YOUR_12_DIGIT.signin.aws.amazon.com/console. We can change YOUR_12_DIGIT to any unique text not used before. The link is available on IAM > Dashboard.

5) It is a good practice to enable MFA(multi factor authentication- 2FA) for root users.

6) We can define password policy. This policy may cover last 5 passwords should't be same or reset your passworf after 90 days etc.

![password_policy](./images/013.png)

7) After creating an IAM user, do one of the followings

    - link user to a group
    - copy permissions of a group to IAM user
    - Attach existing policies directly to IAM user

8) We can create a custom policy. An example is that S3 service can only be accessed with read and list authorizations. While creating a new user, we can assign this custom policy to new user.

9) We can create a role. For example, we want our EC2 instance to access S3 with full access. Role can make it.

### S3

1) S3 is the file storage of AWS. S3 is an object based storage service. S3 stores data as objects in buckets. Buckets are composed of objects. Object = File + Metadata. You can't install an OS on S3. S3 is similar to Microsoft Onedrive, Google Drive, Apple iCloud.

2) Block based vs Object based storage(File based storage)

![s3](./images/014.png)

3) Buckets can be thought as containers for objects. We can have more than 1 bucket. Buckets are region based. Bucket names should be unique among all buckets.

4) We can store our data in 3 different tiers. Storage classes can be modified for objects too.
    - Standard S3: Objects are copied on 3 AZ's. 99.99% availablity.
    - Standard IA(Infrequent Access): Stored on 3 AZ'S. 99.9% availability.
    - Standard 1-zone infrequent access: 1AZ, 99.5% availability

5) S3 is an option named S3 Intelligent-Tiering. This option moves objects to the most appropriate tier(Standard or Standard IA) automatically.

    - Intelligent Tiering Archive Configuration(Under Properties)
    - Standard S3 -> Standard IA -> Archive(Glacier) -> Deep Archive(Glacier)

6) Glacier is similar to S3 but different than S3. It should store objects who aren't required to access fast. It is so cheap. It is acting more like an archive. Access time is around 4-5 hours.

7) We can write some rules to move objects to another layer. One rule might be that if the age of the object is bigger than 30 days but lower than 60 days, move it to Standard Infrequent access If it is bigger than 60 days, move it to Glacier.

8) Storing objects in S3 is cheaper than accessing it.

9) We can store data of our applications in S3. This is what differs S3 from Dropbox or Google Cloud.

10) S3 offers

    - read after write consistency after PUTs of new objects in all regions.
    - offers eventual consistency for overwrite PUTs and DELETE

11) ARN means Amazon Resource Name. It has a pattern  like arn:aws:s3:::my_bucket_name_here. my_bucket_name_here is the name of bucket. It is used from other services aiming to access it.

12) An example S3 URL is below: 

    - https://my_bucket_name_here.s3.amazonaws.com/folder_to_file/CV_Muhammed_Buyukkinaci.pdf

13) We can encrypt S3 objects in server side via Amazon AES-256 or AWS-KMS(Key management system).

14) Object = File + Metadata. Metadata means data about file. One metadata might be size of file, another one might be extension of file, another one might be length of file etc. We can retrieve and update metadata through our apps.

15) Tags can be useful in calculating invoices. Let's assume there are 4 teams in our IT department. We want to know which departman is spending least and most. To learn this, tell teams add tags to their objects programatically. Finally, we can learn which teams spends most. Tags can be assigned to objects or buckets. After assigning a tag, we can access these tagged things(objects or buckets) via Resource groups. Tags are used in invoicing.

16) Object lock is a feature on bucket level. It prevents objects from being deleted. This feature is only active in creating the bucket.

17) Select from is a feature on object level. It is making possible to take a glance to csv, json objects in the bucket without downloading the objects.

18) Versioning in S3 is similar to git. It is off by default. If you turn it off, you can only suspend after turning on. After turning on, we are versioning all changes in a file. If we delete an object from the bucket, it isn't deleted in reality & it is labelled as Delete Marker. It is stored in the background. Our API Calls or CLI Requests will not return the deleted objet. However, we can access the deleted object via AWS Console. If we want to restore deleted object, we should delete "delete marker".

19) Server access logging is a feature on bucket level. It is saving loggings about request directing to S3 objects. If we want to save loggings for our main S3 bucket, we should create a bucket specific to logging and attach logging bucket to main bucket. While creating this logging bucket, choose *Grant Amazon S3 Log Delivery group write access to this bucket*.

20) Object Level Logging is a feature on bucket level. It is similar to Server Access Logging. It is moving data that who accessed our objects etc to CloudTrail service.

21) Static Web Hosting is a feature on bucket level. We can host our static websites on S3.

22) We can make encryption operations on bucket level as object level.

23) Transfer acceleration is a feature on bucket level. It is a paid feature. Let's assume you want to upload a file bigger than 2 TBs. You can upload this file to S3 regularly in 20 days. You can enable transfer acceleration feature to speed up the process. It may take 10 days thanks to transfer acceleration. AWS makes this possible via its CDN network. This feature probably works in the following way. AWS takes the file to its CDN Network first. Then, AWS moves the file to S3 bucket via CDN network. CDN works faster than public internet.

24) Events is a property on bucket level. If you want to trigger an event derived from your existing bucket, you can use this feature. Let's assume you uploaded an image to S3 and want to run image processing code using AWS lambda. You can make it via events. You can connect events to SQS(moving data uploaded to S3 to a queue ) or SNS(sensing an email)

25) Requester pays is a feature on bucket level. You have to block public access to enable it. It is a feature that is charging the requester(An AWS account) trying to acces the object in S3 bucket.

26) ACL abbreviates Access Control List. We analyzed this feature on object level. However, it is also available for bucket level. ACL means who can access to this bucket.

27) Bucket policy is an extended version of ACL. Let's assume you want IP1 to access the bucket with read&write permissions but IP2 to access with read permissions. This is possible with bucket policy. It is more complex than ACL but it is more flexible for our desired settings. We also block IP's aiming to access the bucket. Take a look at [this example](./files/BucketPolicyOrnek.txt)

28) CORS means Cross Origin Resource Sharing. Let's assume you want to store CSS files of your website(muhammedbuyukkinaci.com) in S3 bucket. S3 will check if muhammedbuyukkinaci.com has access to S3 bucket when loading the request. CORS settings should be activated to enable this. Take a look at [this example](./files/CorsOrnek.txt)

29) Block public access is feature on bucket level. It blockes all public requests by default. If you give access via ACL or bucket policy and block public access is active, public access is disabled due to block public access. Block public access is another & high-level tier for security.

30) Lifecycle rules(under Management) is enabling you to define rules for tiers. One example rule might be move files whose age is bigger than 40 days to S3 Glacier. We can filter objects exposed to rules. Let's assume you want to transfer txt files starting with **tech_** to 1 zone availability tier and not move other files to 1 zone availability tier. We can automatically delete markers for versioned objects after a certain days. We can automatically incomplete multipart uploads.

31) Replication(under Management) is copying the content of an existing bucket to another bucket on another region. Let's assume we have a bucket located in Ireland. We want to have a replication of this bucket in USA. By enabling this feature, we can have a replication in USA. Replication is cross-region, which means the destination bucket should be located differently than source bucket.

32) Analytics(under Management) is showing reports about our objects & tiers. It gives us suggestions about moving objects to another tier. It creates reports about usages of objects etc.

33) Metrics(under Management) is showing usage data about storage, requests and data transfer.

34) Inventory(under Management) is showing us which files are in the bucket by reporting daily or weekly.

35) Access Point is a property on bucket level. In previous times, all applications using the same S3 bucket were accessing to S3 bucket via the same ARN(Amazon Resource Name). However, this made things complicated. Therefore, AWS introduced access points. We can access to same S3 bucket from different applications using different access points. We can configure on access point level. A VPC(Virtual Private Cloud) or Internet can be selected for who can access to S3 bucket. We can also define access point policies. An example access point policy is that only this IAM user should access to this bucket and that user should only access to these files(starting with myfirmname_). Access point is changing ARN and object urls for each access point. An example ARN and Object url via access point are below:

    - arn:aws:s3:region_is_here:1111111111111:accesspoint/accesspoint_name_is_here/object/file_name_here.pdf

    - https://accesspoint_name_is_here-1111111111111.s3-accesspoint.region_is_here.amazonaws.com/file_name_here.pdf

36) Object Lambda Access Point is a new feature of S3 on S3 level. Let's assume you want to download 1000 images from the S3 bucket via your program. However, you want to download a zipped version for convenience. In this scenario, Object Lambda Access Point is an intermediary that takes images from S3 and zips them all in a custom Lambda Function. You are triggering object lambda to get zipped version of images. If object lambda access point is used, its ARN is different than bucket ARN. You should use ARN of Object Lambda Access Point instead of Bucket ARN.

37) We can make some kind of operations on all objects in a S3 bucket. This is called batch operations. It is on S3 level. Possible operations are below in the photo. First step to do this is to list all objects in the bucket via Inventory. Then, use the output(csv file) of Inventory in batch operations as an input.

![batch_operations](./images/015.png)

38) Access Analyzer is a new feature. It is analyzing who accessed to our S3 buckets. It is detecting anomally situations like this IP address accessed to this bucket 1000 times a day etc. It should be enabled in IAM console first. Then, it should be activated for S3 level.

39) Storage Lens is showing us dashboards about different statistics. It is on S3 level. These statistics may be the number of objects in the S3 bucket, total size of S3 bucket etc. Advanced statistics are paid but simple statistics are free. 

### CLI

1) Glacier only allows us to use itself via CLI or SDK. UI of Glacier is existing but it is restricted.

2) After installing AWS CLI, the first step is to enter our credentials that we downloaded while creating our IAM user. Run `aws configure` and enter 
    - AWS access key and: 123123afasdasdasdpyt
    - Secret Access Key: 11111aawwe
    - Default region: eu-west-1
    - Default Output Format: json

3) CLI works in the following way: `aws SERVICE_NAME PARAMETER`. An example is `aws s3 list`. To get help, run `aws help` or `aws s3 help` or `aws s3 ls help`. To list objects in S3 bucket, run `aws s3 ls s3://bucket_name_is_here`

### Glacier

1) If you have to store files for 10 years but you may need to access it once in 10 years, Glacier does this exactly. It is appropriate for archiving Customer Agreements.

2) It is a cold data service. It is actually for archiving, not for storing. You can't access to Glacier S3. You should create a function to move files in Glacier to S3.

3) Its access time is around 3 hours. It is not fast as S3.

![glacier](./images/016.png)

4) Glacier -> Vault(Sales or HR etc) -> Archive. S3 -> Bucket. You can access only to Vaults on AWS Console . To access to archives, use CLI or SDK.

5) To create a Vault on CLI

```
aws glacier create-vault --account-id - --vault-name myvault
```

6) Glacier is more complicated than other AWS services.

7) We can't know everything about AWS. It is more complicated than we assume. Always look at AWS tutorials.

### EC2

1) The most used AWS service is EC2.

2) Different Pricing Options:
    - On demand: It is a service of pay as you use. It is hourly charged. Used for testing purposes.
    - Reserved Instance(RI): You promise to use AWS more than 1 year. It is cheaper by 30 percent or more.
    - Scheduled Reserved Instance: Let's assume you want to run a VM between 8:00 am and 5:00 pm. YOu also promise to use this service more than 1 year.
    - Spot: Based on offer. You bid 0.004 dollar for a VM. Your offer matches if your price is above the limit. If it doesn't match, your VM got closed. Some third party firms launched some programs to automize bidding for spot machines.
    - Dedicated Host: A physical machine dedicated for us. We chose this due to some regulations.

3) EC2 Instance Types

![ec2_instance_types](./images/017.png)

4) M5 means fifth generation of M servers. C4 means fourth generation of C.

5) ECU means elastic compute unit. It is showing us the performance of CPU. The more the better. It is a term introduced by AWS to compare CPU performances.

6) Large and Xlarge EC2 instances.
![large](./images/018.png)

7) AWS launced arm64 based CPU servers. They are named as A1.

8) AWS uses Intel CPU's generally. Recently, AWS also collaborated with AMD to release new servers wtih AMD CPU. They are cheaper by 10 percent on average. These new servers are under the category of M5a and T5a.

9) [https://instances.vantage.sh/](https://instances.vantage.sh/) is a website comparing different EC2 instances.

10) Instance store(Ephemeral) is something that is built on a physical server. It is faster but vulnerable to problems. The problems might be electicity cutoffs, hardware problems. The data isn't protected therefore it is lost. Snapshot isn't available.

11) Elastic Block Store(EBS) is a storage type that we can install an OS on top of it. It is separating data from OS. Snapshot is available. It is block based. It is less vulnerable to problems.

![EBS](./images/019.png)

12) IOPS means input output per second. The more the better. It is bigger in SSD's rather than HDD's. It is similar to 0-100 speed of a car.

13) Throughput means the volume of work done. The more the better. It is bigger in HDD's rather than SSD's. It should be big enough for big data servers.

![EBS_storage](./images/020.png)

14) AMI(Amazon Machine Image) is providing us with an OS. AMI can be public(ubuntu, centos) or private(an OS that a firm installed its own SaaS on top of it).

15) ENA means Enhanced Network Adapter. It is enabled or disabled.

16) Hypervisor can be HVM or paravirtual. Paravirtual became obsolete. Most VM's chose Hypervisor.

17) We can choose IAM role(EC2 to S3 connection etc.) or create a new IAM role when creating an EC2 instance.

18) Shutdown Behavior might be Stop or Terminate. These options mean what to do when shutdowning the computer. Stop means paying for the disc consumed. Terminate is killing off the VM and its data.

19) Termination Protection means whether you can terminate the VM using API or CLI or not.

20) Monitoring is normally carried out once in 5 minutes. If it is enabled, it is carried out once in a minute. This is a paid service if enabled.

21) Tenancy means whether the VM runs on a shared or a dedicated machine.

22) We can append new storages to a VM. These storages can be an SSD or HDD etc. We can arrange the capacity of the disc appended.

23) We can add tags to EC2 instances.

24) Security group can be thought as a security wall in front of this VM. All trafic directing to a VM is blocked by default. We can add rules to a security group.

    - Firstly, create a security group.
    - Secondly, add this security group to your VM.
    - Thirdly(Optional), add the security group to another VM you created. 

![security_group](./images/021.png)

25) We can create an AMI(Amazon Machine Image) from a VM. It is similar to creating a docker image from a container.

26) We can see public IP of our EC2 instance, system status, monitoring(CPU utilization, Disc reads, Disc writes etc. )

27) To connect to an EC2 instance from our local computer.

```connect.sh
# set permissions
chmod 400 file_name_is_here.pem
# connect code
ssh -i file_name_is_here.pem ec2-user@IP_V4_IS_HERE
# move to root user
sudo su
# to list buckets in ec2 instance(because we assigned roles when creating instance).
# we can change it in AWS Console later.
aws s3 ls
# to copy a file from s3 to ec2 instance
aws s3 cp s3://bucket_name_is_here/object_name_in_bucket /path/in/ec2

```

28) Putty is an SSH client for Windows. It is also available in Linux. It doesn't support ppm files. Thus, it is required to convert ppm file to ppk.

29) We can write some shellscript code before VM started.

#### ELB - Elastic Load Balancing

30) ELB means Elastic Load Balancing. Load balancer is a network device in reality. You are configuring the request to the device first, then the device directs the requests to VM'S behind itself.

31) Illustration of Load Balancing

![elb_illustration](./images/022.png)

32) Different Types of ELB. Classical Load Balancer serves since 2009. Network Load Balancer work in layer 4, which means no check for packets received, but just directs. Application Load Balancer work in layer 7, which read packets receieved and directs according to packets. If we need a fast & simple LB service for TCP ports, Network Load Balancer should be our choice. If we need to deal with containers, http, https etc, the choice should be application load balancer.

![elb_types](./images/023.png)

#### AutoScaling

33) Autoscaling is automatically adding a VM or removing a VM according to requests. The automatic process is dependent on our custom rules. THe rule might be that add a new VM if CPU usage exceeds 90% for 5 minutes and remove a VM if its CPU usage becomes below under 30%.

#### Placement Group

34) Placement Group is not used frequently. However, it is asked in the exam.

![placement_group](./images/024.png)

35) Placement Group is putting our VM's in a group. It is mostly on the same physical machine(placement group) or in the cluster of physical machines(spread placement group). This feature is especially useful in the case of low latency and high throughput. VM's in the same placement group should have the same server type(C2 or M3 etc). VM's should be created at the same time(4 of them now, 2 of them tomorrow isn't recommended).

