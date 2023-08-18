# DevOps with AWS

To share your interview experience and questions, Add a new file with name in the below format.

<no-of-years>-<designation-of-interview>-<company-name>
 Interview Question
Effective communication and collaboration between DevOps engineers and developers is essential for delivering high-quality software and maintaining smooth operations. Here are some ways DevOps engineers can communicate and collaborate with developers:

When a developer's code deployment fails, DevOps engineers play a crucial role in handling the situation effectively. Here's a step-by-step guide on how DevOps engineers can handle a failed code deployment:

How do you clean your Apache server logs without deleting it? - Log rotation(sudu apt-get install logrotate)
If you must clear the log file, do cp /dev/null /var/log/file or echo > /var/log/file That truncates the file without closing any open file handles. Edit: Using logrotate to deal with the files is the better long-term solution. Truncating the file should be an emergency measure.
How do you check your CPU utilisation? – “top” command,  CAT /prog   cat /proc/loadavg/ or CloudWatch Management Console, you select “Metrics” and then view metrics for EC2. The “CPUUtilization” metric displays your average CPU utilization:
1.	How do you check the memory utilisation of a Linux machine?- free -h
The following commands can help you check memory usage in Linux in different ways.
•	free Command
•	/proc/meminfo File
•	vmstat Command
•	ps_mem Command
•	smem Command
•	top Command
•	htop Command
•	glances Command

2.	The free command has multiple options to format the output so that it better matches your requirements. The table below lists the most useful variations of the free command.
Options	Result
-b	output in bytes
-k	output in kibibytes
-m	output in mebibytes
-g	output in gibibytes
-l	detailed low and high memory statistics
-o	old format (no -/+buffers/cache line)
-t	total for RAM + swap
-s	update every [delay] seconds
-c	update [count] times
vmstat Command to Report Virtual Memory Statistics.The vmstat command is a useful tool that reports virtual memory statistics.vmstat provides general information about processes, memory, paging, block IO, traps, and CPU activity.

3.	How do I get a particular process ID?- pgrep <Process ID>
4.	Write a script to list all error logs? 
5.	#!/bin/bash
6.	
7.	LOGFILE=/usr/local/etc/backups/test14.log
8.	
9.	(
10.	    echo "$(date "+%m%d%Y %T") : Starting work"
11.	    ... more commands ...
12.	    echo error 1>&2 # test stderr
13.	
14.	    echo "$(date "+%m%d%Y %T") : Done"
15.	) >& $LOGFILE
Or s3 bucket save
To configure the log location using the AWS Data Pipeline CLI in a pipeline JSON file, begin your pipeline file with the following text:
{ "objects": [
{
  "id":"Default",
  "pipelineLogUri":"s3://mys3bucket/error_logs"
},
...

16.	Types of storage types in AWS? – Object, Block & File (S3, EBS & EFS)
17.	What are the differences between EFS and EBS?
	Amazon EBS	Amazon EFS
1.	The full form of Amazon EBS is Amazon Elastic Block Store	The full form of Amazon EFS is Amazon Elastic File System
2.	It is used to provide the block-level storage volumes for the use of EC2 instances.	It is simple to use.
3.	It is mainly used for data that should be quickly accessible and requires long term durability.	It is used in modernize application development
4.	It is suitable for both types of database-style applications -:
1. Those rely on random reads
2. Those rely on random writes.	Industries use this for enhancing content 

18.	What are the storage classes in S3?
There are six S3 storage classes. 
1.	Amazon S3 Standard: This is considered general purpose storage for cloud applications, dynamic websites, content distribution, mobile and gaming applications, and big data analytics.
2.	Amazon S3 Intelligent-Tiering: This tier is useful if your data has unknown or changing access patterns. S3 Intelligent-Tiering stores objects in two tiers, a frequent access tier and an infrequent access tier. Amazon S3 monitors access patterns of your data, and automatically moves your data to the most cost-effective storage tier based on frequency of access.
3.	Amazon S3 Standard-Infrequent Access (S3 Standard-IA): S3 Standard-IA is for data that is accessed less frequently, but requires rapid access when needed. S3 Standard-IA offers the high durability, high throughput, and low latency of S3 Standard, with a low per-GB storage price and per-GB retrieval fee. This storage tier is ideal if you want to store long-term backups, disaster recovery files, and so on.
4.	Amazon S3 One Zone-Infrequent Access (S3 One Zone-IA): Unlike other S3 storage classes which store data in a minimum of three Availability Zones (AZs), S3 One Zone-IA stores data in a single AZ and costs 20% less than S3 Standard-IA. S3 One Zone-IA is ideal for customers who want a lower-cost option for infrequently accessed data but do not require the availability and resilience of S3 Standard or S3 Standard-IA. It’s a good choice for storing secondary backup copies of on-premises data or easily re-creatable data.
5.	Amazon S3 Glacier Instant Retrieval: S3 Glacier Instant Retrieval is an archive storage class that delivers the lowest-cost storage for long-lived data that is rarely accessed and requires retrieval in milliseconds. S3 Glacier Instant Retrieval is ideal for archive data that needs immediate access, such as medical images, news media assets, or user-generated content archives. You can upload objects directly to S3 Glacier Instant Retrieval, or use S3 Lifecycle policies to transfer data from the S3 storage classes.
6.	Amazon S3 Glacier Flexible Retrieval (Formerly S3 Glacier): S3 Glacier Flexible Retrieval delivers low-cost storage, up to 10% lower cost (than S3 Glacier Instant Retrieval), for archive data that is accessed 1-2 times per year and is retrieved asynchronously. It is an ideal solution for backup, disaster recovery, offsite data storage needs, and for when some data occasionally need to be retrieved in minutes, and you don’t want to worry about costs.
7.	Amazon S3 Glacier Deep Archive: S3 Glacier Deep Archive is Amazon S3’s lowest-cost storage class and supports long-term retention and digital preservation for data that may be accessed once or twice in a year. It is designed for customers—particularly those in highly-regulated industries, such as financial services, healthcare, and public sectors—that retain data sets for 7-10 years or longer to meet regulatory compliance requirements. S3 Glacier Deep Archive can also be used for backup and disaster recovery use cases, and is a cost-effective and easy-to-manage alternative to magnetic tape systems, whether th

How do you give permission to others to access your S3 bucket? https://dev.to/this-is-learning/setting-bucket-permissions-in-s3-hands-on-2j7k

What are S3 bucket policies
? Here are some of the actions that can be controlled by S3 bucket policies:
1.	GetObject: Allowing users to read objects (files) from the bucket.
2.	PutObject: Allowing users to upload objects to the bucket.
3.	DeleteObject: Allowing users to delete objects from the bucket.
4.	ListBucket: Allowing users to list the contents of the bucket.
5.	DeleteBucket: Allowing users to delete the bucket itself.
19.	

20.	What is Acls in S3? Policies can implement very complex rules and permissions, ACLs are simplistic (they have ALLOW but no DENY).
21.	What are IAM roles?
IAM (Identity and Access Management) roles are a fundamental part of AWS (Amazon Web Services) security and access control. They are used to delegate permissions securely to entities within AWS, such as AWS services, IAM users, or external federated users (e.g., users from your corporate directory).
Instead of directly assigning permissions to individual IAM users, roles allow you to define a set of permissions and then assign those roles to entities that need them. This approach offers several advantages, including improved security, ease of management, and better scalability. IAM roles can be assumed by trusted entities, and they don't have permanent credentials associated with them.
Here's how IAM roles work:
1.	Define a Role: First, you create an IAM role and specify the permissions that it should have. This is similar to creating an IAM policy, but roles are not assigned to specific users directly.
2.	Assign Trust Policy: When creating the role, you attach a "trust policy" to it. The trust policy determines which AWS entities are allowed to assume the role. This could be an AWS service or specific IAM users/groups/roles from your account.
3.	Assume Role: Once the role is created and the trust policy is set up, entities that are allowed by the trust policy can "assume" the role. When assuming the role, the entity effectively takes on the permissions defined in the role.
4.	Temporary Credentials: When an entity assumes a role, it receives temporary security credentials (access key, secret key, and session token). These credentials are valid for a limited time and are automatically rotated by AWS. Temporary credentials help enhance security because they are not tied to long-term IAM user credentials.
IAM roles are commonly used in various scenarios, such as granting permissions to AWS services (e.g., EC2 instances, Lambda functions) so that they can access other AWS resources securely without exposing long-term credentials. Roles are also used for cross-account access, enabling IAM users from one AWS account to access resources in another account without sharing IAM user credentials

22.	What is different between IAM policies and roles?
23.	IAM Policies: IAM policies are the rules or permissions that define what actions are allowed or denied on AWS resources. They can be attached to IAM users, groups, or roles, as well as other AWS resources like S3 buckets or EC2 instances. IAM policies determine the level of access a user or resource has to perform specific actions on AWS services.
24.	IAM Roles: IAM roles are a way to delegate permissions securely. Instead of attaching policies directly to IAM users or groups, roles allow you to define a set of permissions and then assign those roles to trusted entities, such as AWS services or IAM users from other AWS accounts. IAM roles are assumed by trusted entities, and they provide temporary credentials with a limited scope of access.

25.	Types of load balancers?
26.	Classic Load Balancer (4th 7th Layer of OSI)
27.	Application Load Balancer (7th Layer of OSI)
28.	Network Load Balancer -> (4th Layer of OSI) Used for Micro services / container based application
29.	Gateway Load Balancer-> (3rd Layer of OSI)

30.	Which layer of the application load balancer will run?
31.	- An Application Load Balancer (ALB) only works at layer 7 (HTTP). ALB can route requests to many ports on a single target. Plus, ALB can route requests to Lambda functions.

32.	What are the 7 layers of networking?
33.	Physical Layer (Layer 1):
a.	The Physical Layer deals with the physical aspects of network communication. It defines the hardware characteristics, such as cables, switches, hubs, and network interfaces. This layer's primary function is to transmit raw bits over a physical medium without concern for higher-layer protocols or addressing.
34.	Data Link Layer (Layer 2):
a.	The Data Link Layer provides error detection and correction as well as flow control between directly connected devices on the same network segment. It is responsible for framing data into frames, identifying devices using MAC (Media Access Control) addresses, and handling physical addressing.
35.	Network Layer (Layer 3):
a.	The Network Layer handles logical addressing and routing of data between different networks. It is responsible for forwarding data packets from the source to the destination based on IP addresses. Routers operate at this layer, and they use routing protocols to determine the best path for data transmission.
36.	Transport Layer (Layer 4):
a.	The Transport Layer is responsible for end-to-end communication between hosts and provides error recovery and flow control. It ensures that data is delivered reliably and in the correct order. This layer uses port numbers to identify specific applications or services on a device.
37.	Session Layer (Layer 5):
a.	The Session Layer establishes, maintains, and terminates connections between applications on different devices. It manages sessions, which are temporary connections between two applications that need to communicate with each other.
38.	Presentation Layer (Layer 6):
a.	The Presentation Layer is responsible for data format and encryption/decryption. It ensures that data exchanged between applications on different systems is in a readable and understandable format.
39.	Application Layer (Layer 7):
a.	The Application Layer represents the actual applications and services used by end-users. It provides an interface between the user and the network, allowing applications to access network services for communication. Protocols like HTTP, FTP, SMTP, and DNS operate at this layer.

40.	What is VPC?
41.	How do you secure your VPC?
42.	Why do we need VPC?
43.	What is IGW?
44.	What is the NACL?
45.	How do you container CPU utilization? Docker Stats
46.	What is the backend process in Terraform?
Terraform provides the option to store the state file remotely rather than locally. Storing the state remotely has several advantages, such as enabling collaboration among team members and ensuring that the state is accessible from multiple locations. Common remote backend options include Amazon S3, Azure Storage, Google Cloud Storage, and HashiCorp Consul.
47.	What were the providers you used on Terraform?
48.	What are Terraform modules?
49.	How you use modules in your project?

50.	Where do you store your modules?
51.	Version Control Repositories (e.g., GitHub): Many teams choose to store their modules in version control repositories like GitHub, GitLab, or Bitbucket. This approach makes it easy to collaborate on modules and share them across different projects. You can reference a module using a URL:
    hcl
    module "vpc" {
      source = "github.com/myorg/my-vpc-module"
    }

56.	What are pods and containers in Kubernetes?
57.	What is the difference between a stateful set and a deployment set?
58.	What is the Ansible Vault?
59.	What is the Ansible Galaxy?
60.	Can you write a playbook with handlers?
61.	How do you write a playbook for three-tier architecture?
62.	What is an ansible role?
63.	What is the directory that will be created when you do the ansible role command?
64.	How do you create an encrypted playbook?
65.	How do you decrypt your playbook?
66.	What is the biggest troubleshooting done by your carrier?
67.	What problems did you encounter with Ansible, and how did you resolve them?
68.	How do you set the master and slave concepts in Jenkins?
69.	What is NS & A record
70.	What is CName record
71.	What are the types of records in Route53?
72.	What is TTF
73.	What is VPC
74.	What are the components of VPC
75.	What is transit Gateway?
76.	Different between nat gateway and nat instance which you prefer & why? 
77.	What taint in Terraform?
78.	What is ansible playbook, can you able write a playbook?
79.	What is your daily activity?
80.	What is proxy & reverse Proxy?
81.	What is load balancer & it types?
82.	What you done in Terraform? 
83.	What are different between s3 & efs?
84.	What is difference between declarative & scripted pipeline?
85.	How to check connected port with the Linux sever?
86.	How do you check disk usage for different volumes Linux server?
87.	Which ticketing tool you worked?
88.	What is the main configuration file for Maven? 
89.	What configuration you done by using ansible?
90.	What are the models in ansible?
91.	 In Terraform how do you call modules
92.	 How do remove services with using Terraform destroy
93.	What is file module in ansible
94.	What is handlers in ansible
95.	In Jenkins without no pop error pipeline again & again after success without doing anything.
96.	What are the stages in your pipeline
97.	Difference between s3 bucket & Ebs
98.	If SSH key missed how do you connect the server
99.	
100.	
101.	
102.	
103.	






How do you deploy on load Balancer?
Types Environment?
Shared Library?
How you connect Ec2 with terraform?
If terraform Instance down what you do? 
How do you Deploy instance? 
Did you work on Jenkins Workspace? 




company-name is optional.
