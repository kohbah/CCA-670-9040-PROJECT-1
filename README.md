



Cloud Orchestration and Automation Report
Marcel Agyebit Kohbah
University of Maryland Global Campus
 
 
 
 
 
 



 
 
 
 
CCA 670 9040 Capstone: Cloud Computing Orchestration (2208)
Dr. Shawn Khan
October 27, 2020




Cloud Orchestration and Automation Report

Executive Summary 
This report will provide an overview of Cloud Orchestration and Automation with examples of the industry-leading approaches. Some of the approaches that will be explained will be AWS CloudFormation, Terraform, Ansible, and Chef.  This report will provide An overview of AWS Cloud Orchestration and Automation tools such as CloudFormation, elastic container service, AWS OpsWorks, and AWS Systems Manager will be given. AWS CloudFormation features will be reviewed in detailed CloudFormation templates, CloudFormation stacks, CloudFormation change sets, and CloudFormation stacksets. This report will provide an AWS CloudFormation Runbook showing the steps to create a dual-region environment using AWS CloudFormation Stacksets will be given. All the templates that will be used on this runbook are stored on the GitHub repository https://github.com/kohbah/CCA-670-9040-PROJECT-1.  In this report, Cloud Orchestration and Automation Recommendations will be given. Finally, a conclusion on Cloud Orchestration and Automation approaches will be given.



Plan Scope 
This document is for BallotOnline’s IT engineering team. This document will address some of BallotOnline's DevOps team's cloud needs, cloud engineers, system engineers, network engineers, system administrators, database administrators, security teams, and developers. It will be providing a runbook to deploy AWS cloud resources through AWS CloudFormation. This report assumes that you have an AWS cloud account with administrative rights. This document also assumes you have access to this GitHub repository https://github.com/kohbah/CCA-670-9040-PROJECT-1 which is publicly accessible. 
Cloud Orchestration and Automation Overview
What is Cloud Orchestration? Cloud orchestration is the process of managing these multiple workloads, in an automated fashion, across several cloud solutions, with the goal being to synthesize this into a single workflow (DeMuro, 2019). It involves managing a more extensive cloud infrastructure setup in cloud environments. 
What is Cloud Automation? Automation, generally speaking, means completing a single task or function without human intervention. When  Executed wisely, automation makes traditionally time-intensive, manual processes more efficient and reliable. 
In IT, it’s possible to automate a wide range of processes and tasks, from app deployment and integration to securing endpoints and creating service tickets, for both on-premise and cloud tasks (Keen, 2019).

Industry-Leading Cloud Orchestration and Automation Approaches Overview 
Below are some of the leading Industry Cloud Orchestration and Automation Approaches:
	Leading Cloud Orchestration Approaches:
Most Cloud orchestration tools can be used both on-premises and in the cloud. Some examples of cloud Orchestration tools are:
-	CloudFormation: AWS CloudFormation, as the name implies, is a way to "form the cloud" -- meaning, it allows companies to manage and control the application stacks and resources needed for your web and mobile applications. It provides access to infrastructure components at your disposal and will enable you to manage them all from one central command-line interface (Brandon, 2020).
-	Terraform: Terraform is a tool for building, changing, and versioning infrastructure safely and efficiently. Terraform can manage existing and popular service providers as well as custom in-house solutions. Configuration files describe to Terraform the components needed to run a single application or your entire datacenter. Terraform generates an execution plan describing what it will do to reach the desired state and then executes it to build the defined infrastructure (“Introduction,” n.d.).

	Leading Cloud Automation Approaches:
Some of the leading cloud automation approaches are: 
-	Ansible: Ansible is a software tool that provides simple but powerful automation for cross-platform computer support. Ansible is primarily intended for IT professionals who use it for application deployment, updates on workstations and servers, cloud provisioning, configuration management, intra-service orchestration, and nearly anything a systems administrator does on a weekly or daily basis (“What is Ansible?,” n.d.).

-	Chef: Chef is a configuration management tool for dealing with machine setup on physical servers, virtual machines, and the cloud. Many companies use Chef software to control and manage their infrastructure, including Facebook, Etsy, Cheezburger, and Indiegogo (McIvor, 2015).

Cloud Orchestration and Automation in AWS (2–3 pages)
AWS Cloud provides both Cloud Orchestration and Automation services that are industry standards. 
	Cloud Orchestration in AWS:
-	CloudFormation: AWS CloudFormation, as the name implies, is a way to "form the cloud" -- meaning, it allows companies to manage and control the application stacks and resources needed for your web and mobile applications. It provides access to infrastructure components at your disposal and will enable you to manage them all from one central command-line interface (Brandon, 2020).

-	Elastic Container Service: Amazon Elastic Container Service (Amazon ECS) is a fully managed container orchestration service. Customers such as Duolingo, Samsung, GE, and Cookpad use ECS to run their most sensitive and mission-critical applications because of its security, reliability, and scalability (“Amazon Elastic Container Service,” n.d.).


	Cloud Automation in AWS:
-	AWS OpsWorks: AWS OpsWorks is a configuration management service that helps you configure and operate applications in a cloud enterprise by using Chef. AWS OpsWorks Stacks and AWS OpsWorks for Chef Automate let you use Chef cookbooks and configuration management (Kumar, 2020).
-	AWS Systems Manager: AWS Systems Manager is an AWS service that you can use to view and control your AWS infrastructure. Using the Systems Manager console, you can view operational data from multiple AWS services and automate operational tasks across your AWS resources. Systems Manager helps you maintain security and compliance by scanning your managed instances and reporting on (or taking corrective action on) any policy violations it detects (“What is AWS Systems Manager? - AWS Systems Manager,” n.d.).

AWS CloudFormation Feature Review
Some of the features and concepts used in AWS CloudFormation are: 
-	Templates: CloudFormation templates are YAML and JSON style formatted files that define resources and steps to deploy AWS resources. A template can be saved on an S3 bucket or local computer and uploaded into your CloudFormation when defining the stack to be created. 
-	Stacks: a stack in AWS CloudFormation is made up of all the resources being defined into the CloudFormation template to be created. A stack is made up of predefined resources in the AWS template, such as ec2 instance, S3 buckets, ECS containers, load balancers, and VPC. 
-	Change sets: when you need to make changes to your AWS stack, you will need to generate a change set that will show the changes you will be making.
-	Stacksets: when your AWS infrastructure grows more extensive, and you decide to run a multi-account and region application setup, it is best advised to use a more advanced feature of AWS CloudFormation called stacksets. A stackset will enable you to create, update, and delete CloudFormation stacks across multiple accounts and regions.  
Summary
Though CloudFormation is an industry-leading cloud Orchestration service, it can only be used within AWS Cloud. AWS CloudFormation can not be used with other cloud providers, unlike terraform, Ansible, and Chef.


AWS CloudFormation Runbook
In this runbook, one will learn how to build a dual-region environment using AWS CloudFormation StackSets. Each region will contain an Amazon VPC and an Amazon Linux 2 instance running a LAMP (Linux/Apache/MariaDB/PHP) stack.

Prerequisites and Assumptions
-	Access to an AWS account.
-	Administrator access to the AWS account.
-	Basic knowledge of AWS management console. 
-	Access and download this GitHub repository with all the below documents on the screenshot (https://github.com/kohbah/CCA-670-9040-PROJECT-1)
 

The steps to follow for this runbook are as follows: 

1. Choose two regions
You will have to select two regions. One will be the administrative (us-east-1) account, which will contain the CloudFormation stackset. The stacks will be running in two regions, that is us-east-1 and us-west-2. 

 

2. Locate your AWS account ID
Locate your AWS account ID to be used as an input into the CloudFormation Template. Sign in to your AWS account and locate your AWS account ID from your account's top right corner (click on support). For this current account, the account ID is 877510168756.

 

3. Set up IAM roles for AWS CloudFormation StackSets
AWS Cloudformation StackSets requires two IAM roles to install stacks across regions which are: 
	AWSCloudFormationStackSetAdministrationRole
	AWSCloudFormationStackSetExecutionRole
To create these roles, go through the following steps.

3.1.1 Go to the CloudFormation console. 

3.1.2 Set your region to the administrative region (us-east-1 in this example).

3.1.3 Click Create Stack.

3.1.4 Click “Upload a template file” and specify the file “AWSCloudFormationStackSetAdministrationRole” downloaded from this git repository https://github.com/kohbah/CCA-670-9040-PROJECT-1 and click Next. 
 

3.1.5 Enter StacksetAdministrationRole for the name of the stack and click Next.
3.1.6 Click Next again.
 


3.1.7 Check the Acknowledge box to acknowledge that you are creating IAM resources and click Create. 
 

3.2. From the CloudFormation console, verify if the CloudFormation stack was successfully created. Go to the IAM Console, select Roles, and see if the role named AWSCloudFormationStackSetExecutionRole already exists. 
 
 

3.2.1 Go the CloudFormation console.

3.2.2 Set your region to the administrative region (us-east-1 in this example).

3.2.3 Click Create Stack.

3.2.4 Click “Upload a template file” and specify the file “AWSCloudFormationStackSetExecutionRole.yml” downloaded from this git repository https://github.com/kohbah/CCA-670-9040-PROJECT-1 and click Next. 
 
3.2.5 Enter “StacksetExecutionRole” for the name of the stack and click Next. For the field AdministratorAccountId, enter your AWS account ID that you saved from section 2 and click Next.
 

3.2.6 Click Next again.

3.2.7 Check the Acknowledge box to acknowledge that you are creating IAM resources and click Create. CloudFormation will begin to create the role. Refresh the screen to update the status. Wait until the status changes to CREATE_COMPLETE. If the stack rolls back, it likely means that the AWSCloudFormationStackSetExecutionRole role already exists.
 
 

4. Create the EnableCloudTrail StackSet
Now you have to create a StackSet, which represents a CloudFormation template that has been deployed. A stack set lets you create stacks in AWS accounts across regions by using a single AWS CloudFormation template. All the resources included in each stack are defined by the stack set's AWS CloudFormation template ("StackSets concepts - AWS CloudFormation,” n.d.).
4.1 Go to the CloudFormation console. Ensure you are in the administrative region (us-east-1 in this example) and select StackSets from the drop-down menu and click Create StackSet. 
 
Under Choose a template, Select “Template is ready” and upload the file EnableCloudTrail.yaml from the GitHub repository (https://github.com/kohbah/CCA-670-9040-PROJECT-1).  
 

4.2 On the Specify Details page, enter EnableCloudTrail for the stack name and accept all the other fields' default values. Click Next. 
 

4.3 Under “Configure StackSet options," select "Self-service permissions” and specify the CloudFormation roles created above. Specify the IAM admin and IAM execution role names.
 
4.4 On the Set deployment options page, choose “Deploy stacks in accounts” and specify your account ID. 
 
4.5 Under Specify regions, select both target regions (us-east-1 and us-west-2 in this example) and click Add to move the regions over to the Deployment order column. The order itself is not essential. Click Next.
 
4.6 On the Review page, click Submit.
 

CloudFormation will begin to create the StackSet by delivering the template to each region and building the individual CloudFormation stack in each region. It will take several minutes to deploy the StackSet. 

4.7 Verify Stack instances and make sure Operations Status shows Running during deployment. 
 
 

 4.8 After the StackSet build has been completed, the operation state will change to SUCCEEDED, and the individual stacks will be in a CURRENT state, as shown below. 
 
 

5. Create the CreateVpc StackSet
After creating the CloudFormation templates and StackSet, you now have to create a VPC template. 
5.1 Go to the CloudFormation console and select the administrative region (us-east-1 in this example). Deploy the template as a stack (not a StackSet) in the administrative region (us-east-1 in this example). Upload the file CreateVpc.yaml from the GitHub repository (https://github.com/kohbah/CCA-670-9040-PROJECT-1).  
 
5.2 Provide VPC name and availability zone name for the VPC. Proceed to the review page and click on the create button.  
 
 

5.3 Go to the CloudFormation console in the administrative region (us-east-1 in this example). Select the CreateVpc stack, click Actions, and select Delete Stack to delete the CreateVpc stack.
 
5.4 Deploy the updated CreateVpc2.yaml file as a stack (not a StackSet) within the administrative region (us-east-1). Use vpc2 for the name of the stack. Upload the file CreateVpc2.yaml from the GitHub repository (https://github.com/kohbah/CCA-670-9040-PROJECT-1).
 
 
5.5 Delete vpc2 stack
 

5.6 Deploy the vpcMappings.yaml file from the Github repository (https://github.com/kohbah/CCA-670-9040-PROJECT-1) to map CIDR values for two regions.
 
 
5.6 Deploy the vpcMappings.yaml as a stackset. The file is located on the GitHub repository (https://github.com/kohbah/CCA-670-9040-PROJECT-1) for both regions to have VPC.
 
 

5.7 Provide stackset name as “CreateVpc” and click next. 
 

5.8 Under “Configure StackSet options” for permissions, select “Self-service permissions." Provide admin role ARN and execution role name.  
 
5.9 On the Set deployment options page, choose “Deploy stacks in accounts” and specify your account ID. 
 
5.10 Under Specify regions, select both target regions (us-east-1 and us-west-2 in this example) and click Add to move the regions over to the Deployment order column. The order itself is not essential. Click Next. 
 

5.11 On the Review page, click Submit.
 
CloudFormation will begin to create the StackSet by delivering the template to each region and building the individual CloudFormation stack in each region. It will take several minutes to deploy the StackSet. 
5.12 Verify stackset has been executed successfully through stack instances and operations.
  
 

6. Create the LAMP StackSet
6.1 Deploy the LampParent.yaml as a stack (not a StackSet) in the administrative region (us-east-1).  The LampParent.yaml  file will deploy nested stacks; the file is located on the GitHub repository (https://github.com/kohbah/CCA-670-9040-PROJECT-1). This file is a nested stack that contains values in the Lamp.yaml file. Provide the stack name and database root password. Click next and create the stack. 
 

6.2 Verify the parent template URL from S3 buck (https://s3-external-1.amazonaws.com/cf-templates-x40l3p5w2l19-us-east-1/2020301KVP-LampParent.yaml)
 
6.3 Acknowledge that AWS CloudFormation might create IAM resources with custom names and acknowledge that AWS CloudFormation might require the following capability: CAPABILITY_AUTO_EXPAND.
 
6.4 From AWS CloudFormation console, very if the Lamparent stack has been created as well as the NESTED stack
 

6.5 Clink on the public IP address (from the Outputs section of CloudFormation) provided by the LampInstanceUrl is a hyperlink. Click on that hyperlink, and you should see the Apache test page. 
 
 

6.6 Delete the LampParent stack (not the nested stack). The nested stack will automatically be deleted after deleting the LampParent stack. Wait for the deletion of both stacks to complete. 
 

6.7 Deploy the LampParentFinal.yaml as StackSet. The LampParentFinal.yaml  file will deploy a stackset; it is located on the GitHub repository (https://github.com/kohbah/CCA-670-9040-PROJECT-1). This file is a nested stack that contains values in the LampParentFinal.yaml file. This stack will create a lambda role and a lambda function that will output database credentials for both regions. Under Choose a template, Select “Template is ready” and upload the file LampParentFinal.yaml from the GitHub repository (https://github.com/kohbah/CCA-670-9040-PROJECT-1).  

 
6.8 Under “Specify StackSet details," provide the stackset name as LampParentFinal. Click on "Next."
 

6.9  Under “Configure StackSet options” for permissions, select “Self-service permissions." Provide admin role ARN and execution role name.  
 

6.10 On the Set deployment options page, choose “Deploy stacks in accounts” and specify your account ID. 
 

6.11 Under Specify regions, select both target regions (us-east-1 and us-west-2 in this example) and click Add to move the regions over to the Deployment order column. The order itself is not essential. Click Next. 
 

6.12 Acknowledge that AWS CloudFormation might create IAM resources with custom names and acknowledge that AWS CloudFormation might require the following capability: CAPABILITY_AUTO_EXPAND.
 

6.13 Verify the stackset was created successfully, verify the stack instances and operations.  
 
 
6.14 Go to the CloudFormation console in both regions and look at the Output tab. You should see a different value for DbRootPassword in each region. Also, click on the LampinstanceUrl to receive a response from the apache server for each region.
- For US East (N. Virginia) us-east-1
 
 
-	For US West (Oregon) us-west-2
 
 

7. Clean up
7.1 Go to the CloudFormation console in the administrative region (us-east-1 in this example) and manage all StackSet. Delete the stacks in each region and then delete the StackSet itself.
 
7.2 Under "Set deployment options," provide account ID and specify all the regions being used. Click Next and Submit.  
 
 
Repeat steps 7.1 to 7.2 for all other stacksets.
7.3 Go to S3 buckets and delete all S3 buckets created during this demo for each region. 
 

Cloud Orchestration and Automation Recommendations 
AWS CloudFormation is an excellent cloud orchestration tool for AWS, but it cannot be used for other Cloud services. BallotOnline should always try to avoid any vendor lock-in with AWS and using CloudFormation; it will eventually lead to that in the long run. BallotOnline should make sure its CloudFormation templates are versioned either in their AWS S3 bucket or GitHub repository. Before a task is automated into production, BallotOnline should make sure the security team validates the setup's compliances. One of the disadvantages of complete automation is that it can lead to sensitive data like passwords being exposed to those who do not have to see them. More so, before a task is fully automated, the BallotOnline team should make sure it is accompanied by a detailed README.md file or SOP for other users to use them with care per company compliance.


Conclusion 
AWS CloudFormation is a better Cloud Orchestration tool for infrastructure environments on AWS. While this is a significant advantage for AWS resources, Cloud Orchestration can be very disadvantageous with other Cloud service providers such as AZURE, GCP, and VMware. AWS CloudFormation is only supported in AWS and can not be supported by other cloud services providers. Therefore, for some of BallotOnline services that might have a similar deployment in other cloud services providers, it will be better to take advantage of the multi-cloud benefits of terraform. BallotOnline should train its engineers to use CloudFormation and Terraform to avoid vendor lock-in with AWS CloudFormation.  

 












reference
Amazon Elastic Container Service. (n.d.). Retrieved from https://aws.amazon.com/ecs/?whats-new-cards.sort-by=item.additionalFields.postDateTime&whats-new-cards.sort-order=desc&ecs-blogs.sort-by=item.additionalFields.createdDate&ecs-blogs.sort-order=desc
Brandon, J. (2020, January 11). What is AWS CloudFormation? Retrieved from https://www.techradar.com/news/what-is-aws-cloudformation
DeMuro, J. P. (2019, November 18). What is cloud orchestration? Retrieved from https://www.techradar.com/news/what-is-cloud-orchestration
Introduction. (n.d.). Retrieved from https://www.terraform.io/intro/index.html
Keen, E. (2019, March 4). Automation vs. Orchestration: What’s the Difference? Retrieved from https://www.burwood.com/blog-archive/automation-vs-orchestration-whats-the-difference
Kumar, S. (2020, August 31). How to use AWS OpsWorks? Retrieved from https://www.whizlabs.com/blog/aws-opsworks/
McIvor, K. (2015, October 7). DevOps tools: The beginner’s guide to Chef. Retrieved from https://www.theregister.com/2015/10/07/chef_introduction/#:%7E:text=Chef%20is%20a%20configuration%20management,Etsy%2C%20Cheezburger%2C%20and%20Indiegogo.
StackSets concepts - AWS CloudFormation. (n.d.). Retrieved from https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/stacksets-concepts.html
What is Ansible? (n.d.). Retrieved from https://opensource.com/resources/what-ansible
What is AWS Systems Manager? - AWS Systems Manager. (n.d.). Retrieved from https://docs.aws.amazon.com/systems-manager/latest/userguide/what-is-systems-manager.html




