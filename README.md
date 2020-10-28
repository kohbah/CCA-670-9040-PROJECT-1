Running head: Cloud Orchestration and Automation Report

Cloud Orchestration and Automation Report

Marcel Agyebit Kohbah

University of Maryland Global Campus

CCA 670 9040 Capstone: Cloud Computing Orchestration (2208)

Dr. Shawn Khan

October 27, 2020

**Cloud Orchestration and Automation Report**

**Executive Summary**

This report will provide an overview of Cloud Orchestration and Automation with examples of the industry-leading approaches. Some of the approaches that will be explained will be AWS CloudFormation, Terraform, Ansible, and Chef. This report will provide An overview of AWS Cloud Orchestration and Automation tools such as CloudFormation, elastic container service, AWS OpsWorks, and AWS Systems Manager will be given. AWS CloudFormation features will be reviewed in detailed CloudFormation templates, CloudFormation stacks, CloudFormation change sets, and CloudFormation stacksets. This report will provide an AWS CloudFormation Runbook showing the steps to create a dual-region environment using AWS CloudFormation Stacksets will be given. All the templates that will be used on this runbook are stored on the GitHub repository https://github.com/kohbah/CCA-670-9040-PROJECT-1. In this report, Cloud Orchestration and Automation Recommendations will be given. Finally, a conclusion on Cloud Orchestration and Automation approaches will be given.

**Plan Scope**

This document is for BallotOnline&#39;s IT engineering team. This document will address some of BallotOnline&#39;s DevOps team&#39;s cloud needs, cloud engineers, system engineers, network engineers, system administrators, database administrators, security teams, and developers. It will be providing a runbook to deploy AWS cloud resources through AWS CloudFormation. This report assumes that you have an AWS cloud account with administrative rights. This document also assumes you have access to this GitHub repository [https://github.com/kohbah/CCA-670-9040-PROJECT-1](https://github.com/kohbah/CCA-670-9040-PROJECT-1) which is publicly accessible.

**Cloud Orchestration and Automation Overview**

**What is Cloud Orchestration?** Cloud orchestration is the process of managing these multiple workloads, in an automated fashion, across several cloud solutions, with the goal being to synthesize this into a single workflow (DeMuro, 2019). It involves managing a more extensive cloud infrastructure setup in cloud environments.

**What is Cloud Automation?** Automation, generally speaking, means completing a single task or function without human intervention. When Executed wisely, automation makes traditionally time-intensive, manual processes more efficient and reliable.

In IT, it&#39;s possible to automate a wide range of processes and tasks, from app deployment and integration to securing endpoints and creating service tickets, for both on-premise and cloud tasks (Keen, 2019).

**Industry-Leading Cloud Orchestration and Automation Approaches Overview**

Below are some of the leading Industry Cloud Orchestration and Automation Approaches:

- **Leading Cloud Orchestration**** Approaches:**

Most Cloud orchestration tools can be used both on-premises and in the cloud. Some examples of cloud Orchestration tools are:

- **CloudFormation:** AWS CloudFormation, as the name implies, is a way to &quot;form the cloud&quot; -- meaning, it allows companies to manage and control the application stacks and resources needed for your web and mobile applications. It provides access to infrastructure components at your disposal and will enable you to manage them all from one central command-line interface (Brandon, 2020).
- **Terraform:** Terraform is a tool for building, changing, and versioning infrastructure safely and efficiently. Terraform can manage existing and popular service providers as well as custom in-house solutions. Configuration files describe to Terraform the components needed to run a single application or your entire datacenter. Terraform generates an execution plan describing what it will do to reach the desired state and then executes it to build the defined infrastructure (&quot;Introduction,&quot; n.d.).

- **Leading Cloud Automation**** Approaches:**

Some of the leading cloud automation approaches are:

- **Ansible:** Ansible is a software tool that provides simple but powerful automation for cross-platform computer support. Ansible is primarily intended for IT professionals who use it for application deployment, updates on workstations and servers, cloud provisioning, configuration management, intra-service orchestration, and nearly anything a systems administrator does on a weekly or daily basis (&quot;What is Ansible?,&quot; n.d.).

- **Chef:** Chef is a configuration management tool for dealing with machine setup on physical servers, virtual machines, and the cloud. Many companies use Chef software to control and manage their infrastructure, including Facebook, Etsy, Cheezburger, and Indiegogo (McIvor, 2015).

**Cloud Orchestration and Automation in AWS (2–3 pages)**

AWS Cloud provides both Cloud Orchestration and Automation services that are industry standards.

- **Cloud Orchestration in AWS:**

- **CloudFormation:** AWS CloudFormation, as the name implies, is a way to &quot;form the cloud&quot; -- meaning, it allows companies to manage and control the application stacks and resources needed for your web and mobile applications. It provides access to infrastructure components at your disposal and will enable you to manage them all from one central command-line interface (Brandon, 2020).

- **Elastic Container Service:** Amazon Elastic Container Service (Amazon ECS) is a fully managed container orchestration service. Customers such as Duolingo, Samsung, GE, and Cookpad use ECS to run their most sensitive and mission-critical applications because of its security, reliability, and scalability (&quot;Amazon Elastic Container Service,&quot; n.d.).

- **Cloud Automation in AWS:**

- **AWS OpsWorks:** AWS OpsWorks is a configuration management service that helps you configure and operate applications in a cloud enterprise by using Chef. AWS OpsWorks Stacks and AWS OpsWorks for Chef Automate let you use Chef cookbooks and configuration management (Kumar, 2020).
- **AWS Systems Manager:** AWS Systems Manager is an AWS service that you can use to view and control your AWS infrastructure. Using the Systems Manager console, you can view operational data from multiple AWS services and automate operational tasks across your AWS resources. Systems Manager helps you maintain security and compliance by scanning your managed instances and reporting on (or taking corrective action on) any policy violations it detects (&quot;What is AWS Systems Manager? - AWS Systems Manager,&quot; n.d.).

**AWS CloudFormation Feature Review**

Some of the features and concepts used in AWS CloudFormation are:

- **Templates:** CloudFormation templates are YAML and JSON style formatted files that define resources and steps to deploy AWS resources. A template can be saved on an S3 bucket or local computer and uploaded into your CloudFormation when defining the stack to be created.
- **Stacks:** a stack in AWS CloudFormation is made up of all the resources being defined into the CloudFormation template to be created. A stack is made up of predefined resources in the AWS template, such as ec2 instance, S3 buckets, ECS containers, load balancers, and VPC.
- **Change sets:** when you need to make changes to your AWS stack, you will need to generate a change set that will show the changes you will be making.
- **Stacksets:** when your AWS infrastructure grows more extensive, and you decide to run a multi-account and region application setup, it is best advised to use a more advanced feature of AWS CloudFormation called stacksets. A stackset will enable you to create, update, and delete CloudFormation stacks across multiple accounts and regions.

**Summary**

Though CloudFormation is an industry-leading cloud Orchestration service, it can only be used within AWS Cloud. AWS CloudFormation can not be used with other cloud providers, unlike terraform, Ansible, and Chef.

**AWS CloudFormation Runbook**

In this runbook, one will learn how to build a dual-region environment using AWS CloudFormation StackSets. Each region will contain an Amazon VPC and an Amazon Linux 2 instance running a LAMP (Linux/Apache/MariaDB/PHP) stack.

**Prerequisites and Assumptions**

- Access to an AWS account.
- Administrator access to the AWS account.
- Basic knowledge of AWS management console.
- Access and download this GitHub repository with all the below documents on the screenshot **(**[https://github.com/kohbah/CCA-670-9040-PROJECT-1](https://github.com/kohbah/CCA-670-9040-PROJECT-1))

![](RackMultipart20201028-4-1ff9g7_html_be38c89eda4981d6.gif) ![](RackMultipart20201028-4-1ff9g7_html_c9652065acf09ff5.gif) ![](RackMultipart20201028-4-1ff9g7_html_2925e4b73162c005.png)

The steps to follow for this runbook are as follows:

**1. Choose two regions**

You will have to select two regions. One will be the administrative (us-east-1) account, which will contain the CloudFormation stackset. The stacks will be running in two regions, that is us-east-1 and us-west-2.

![](RackMultipart20201028-4-1ff9g7_html_25503aa2a209f90.gif) ![](RackMultipart20201028-4-1ff9g7_html_be38c89eda4981d6.gif) ![](RackMultipart20201028-4-1ff9g7_html_fee455aff6f0adcd.png)

**2. Locate your AWS account ID**

Locate your AWS account ID to be used as an input into the CloudFormation Template. Sign in to your AWS account and locate your AWS account ID from your account&#39;s top right corner (click on support). For this current account, the account ID is 877510168756.

![](RackMultipart20201028-4-1ff9g7_html_4ab50a212179c93f.gif) ![](RackMultipart20201028-4-1ff9g7_html_30ac95e70912b3e.png)

**3. Set up IAM roles for AWS CloudFormation StackSets**

AWS Cloudformation StackSets requires two IAM roles to install stacks across regions which are:

- AWSCloudFormationStackSetAdministrationRole
- AWSCloudFormationStackSetExecutionRole

To create these roles, go through the following steps.

**3.1.1** Go to the CloudFormation console.

**3.1.2** Set your region to the administrative region (us-east-1 in this example).

**3.1.3** Click Create Stack.

**3.1.4** Click &quot;Upload a template file&quot; and specify the file &quot;AWSCloudFormationStackSetAdministrationRole&quot; downloaded from this git repository [https://github.com/kohbah/CCA-670-9040-PROJECT-1](https://github.com/kohbah/CCA-670-9040-PROJECT-1) and click Next.

![](RackMultipart20201028-4-1ff9g7_html_f58392f5a2c83a38.gif) ![](RackMultipart20201028-4-1ff9g7_html_e0f6e30e82c3694f.gif) ![](RackMultipart20201028-4-1ff9g7_html_32658edb650ff310.png)

**3.1.5** Enter **StacksetAdministrationRole** for the name of the stack and click Next.

**3.1.6 Click Next again.**

![](RackMultipart20201028-4-1ff9g7_html_bb1b8a02988a88c0.gif) ![](RackMultipart20201028-4-1ff9g7_html_909360f8df18ccbd.gif) ![](RackMultipart20201028-4-1ff9g7_html_6af2b5cbbaae8cb2.png)

**3.1.7** Check the Acknowledge box to acknowledge that you are creating IAM resources and click Create.

![](RackMultipart20201028-4-1ff9g7_html_84862be2716ef1ca.gif) ![](RackMultipart20201028-4-1ff9g7_html_a81feb89dc33a459.gif) ![](RackMultipart20201028-4-1ff9g7_html_1662a9a047f2a7ed.png)

**3.2.** From the CloudFormation console, verify if the CloudFormation stack was successfully created. Go to the IAM Console, select Roles, and see if the role named AWSCloudFormationStackSetExecutionRole already exists.

![](RackMultipart20201028-4-1ff9g7_html_f542b0f255c53cce.png)

![](RackMultipart20201028-4-1ff9g7_html_74cc69e9f6e19d99.gif) ![](RackMultipart20201028-4-1ff9g7_html_358300ecc024d57b.png)

**3.2.1** Go the CloudFormation console.

**3.2.2** Set your region to the administrative region (us-east-1 in this example).

**3.2.3** Click Create Stack.

**3.2.4** Click &quot;Upload a template file&quot; and specify the file &quot;AWSCloudFormationStackSetExecutionRole.yml&quot; downloaded from this git repository [https://github.com/kohbah/CCA-670-9040-PROJECT-1](https://github.com/kohbah/CCA-670-9040-PROJECT-1) and click Next.

![](RackMultipart20201028-4-1ff9g7_html_9bdecaabc5342f22.gif) ![](RackMultipart20201028-4-1ff9g7_html_e09c85ef94a28db.gif) ![](RackMultipart20201028-4-1ff9g7_html_402c3ee8cbd60941.png)

**3.2.5** Enter &quot;StacksetExecutionRole&quot; for the name of the stack and click Next. For the field AdministratorAccountId, enter your AWS account ID that you saved from section 2 and click Next.

![](RackMultipart20201028-4-1ff9g7_html_2eec4fb772cc0992.gif) ![](RackMultipart20201028-4-1ff9g7_html_9bdecaabc5342f22.gif) ![](RackMultipart20201028-4-1ff9g7_html_2ce5d9d767b8b1ca.gif) ![](RackMultipart20201028-4-1ff9g7_html_e5ce0df022c61d3f.png)

**3.2.6** Click Next again.

**3.2.7** Check the Acknowledge box to acknowledge that you are creating IAM resources and click Create. CloudFormation will begin to create the role. Refresh the screen to update the status. Wait until the status changes to CREATE\_COMPLETE. If the stack rolls back, it likely means that the AWSCloudFormationStackSetExecutionRole role already exists.

![](RackMultipart20201028-4-1ff9g7_html_6cb32ac7b3e08a46.gif) ![](RackMultipart20201028-4-1ff9g7_html_1873fb088030e1fa.gif) ![](RackMultipart20201028-4-1ff9g7_html_9da8e088e0c566cd.png)

![](RackMultipart20201028-4-1ff9g7_html_e536bda044bd7163.gif) ![](RackMultipart20201028-4-1ff9g7_html_efff283b89d21a8e.gif) ![](RackMultipart20201028-4-1ff9g7_html_9308eb59ae8b07a4.png)

**4.** Create the EnableCloudTrail StackSet

Now you have to create a StackSet, which represents a CloudFormation template that has been deployed. A stack set lets you create stacks in AWS accounts across regions by using a single AWS CloudFormation template. All the resources included in each stack are defined by the stack set&#39;s AWS CloudFormation template (&quot;StackSets concepts - AWS CloudFormation,&quot; n.d.).

**4.1** Go to the CloudFormation console. Ensure you are in the administrative region (us-east-1 in this example) and select StackSets from the drop-down menu and click Create StackSet.

![](RackMultipart20201028-4-1ff9g7_html_e5a1ec225a903e99.gif) ![](RackMultipart20201028-4-1ff9g7_html_9b8191def8bbf1e.gif) ![](RackMultipart20201028-4-1ff9g7_html_2a8f4493cb4d6bb1.png)

Under Choose a template, Select &quot;Template is ready&quot; and upload the file EnableCloudTrail.yaml from the GitHub repository ([https://github.com/kohbah/CCA-670-9040-PROJECT-1](https://github.com/kohbah/CCA-670-9040-PROJECT-1)).

![](RackMultipart20201028-4-1ff9g7_html_1554e20cea7d79ae.gif) ![](RackMultipart20201028-4-1ff9g7_html_82893aca5b310ac9.gif) ![](RackMultipart20201028-4-1ff9g7_html_22e6e243532d694b.png)

**4.2** On the Specify Details page, enter EnableCloudTrail for the stack name and accept all the other fields&#39; default values. Click Next.

![](RackMultipart20201028-4-1ff9g7_html_a522f2888d000948.gif) ![](RackMultipart20201028-4-1ff9g7_html_d648ae7da164ff2c.png)

**4.3** Under &quot;Configure StackSet options,&quot; select &quot;Self-service permissions&quot; and specify the CloudFormation roles created above. Specify the IAM admin and IAM execution role names.

![](RackMultipart20201028-4-1ff9g7_html_2e94aeb1d8a47bc.gif) ![](RackMultipart20201028-4-1ff9g7_html_597c1cd6c10ab820.gif) ![](RackMultipart20201028-4-1ff9g7_html_3d75450802f6ba71.gif) ![](RackMultipart20201028-4-1ff9g7_html_65e0e1a5ef49cc99.png)

**4.4** On the Set deployment options page, choose &quot;Deploy stacks in accounts&quot; and specify your account ID.

![](RackMultipart20201028-4-1ff9g7_html_6529fe472445f456.gif) ![](RackMultipart20201028-4-1ff9g7_html_5a658d972819c3ed.gif) ![](RackMultipart20201028-4-1ff9g7_html_c4d93e8b167e3386.png)

**4.5** Under Specify regions, select both target regions (us-east-1 and us-west-2 in this example) and click Add to move the regions over to the Deployment order column. The order itself is not essential. Click Next.

![](RackMultipart20201028-4-1ff9g7_html_d5e0c47c1c5ae057.gif) ![](RackMultipart20201028-4-1ff9g7_html_15286da6d8680826.gif) ![](RackMultipart20201028-4-1ff9g7_html_624fdd0bd4921555.png)

**4.6** On the Review page, click Submit.

![](RackMultipart20201028-4-1ff9g7_html_e8916453e58c9ba2.gif) ![](RackMultipart20201028-4-1ff9g7_html_50ff8bc74b58a0aa.png)

CloudFormation will begin to create the StackSet by delivering the template to each region and building the individual CloudFormation stack in each region. It will take several minutes to deploy the StackSet.

**4.7** Verify Stack instances and make sure Operations Status shows Running during deployment.

![](RackMultipart20201028-4-1ff9g7_html_d71d0590b3f978b2.png)

![](RackMultipart20201028-4-1ff9g7_html_4a371f0cf755f3f2.png)

**4.8** After the StackSet build has been completed, the operation state will change to SUCCEEDED, and the individual stacks will be in a CURRENT state, as shown below.

![](RackMultipart20201028-4-1ff9g7_html_d8471b283ed7ed7a.png)

![](RackMultipart20201028-4-1ff9g7_html_8de3ec3e194c10f4.png)

**5.** Create the CreateVpc StackSet

After creating the CloudFormation templates and StackSet, you now have to create a VPC template.

**5.1** Go to the CloudFormation console and select the administrative region (us-east-1 in this example). Deploy the template as a stack (not a StackSet) in the administrative region (us-east-1 in this example). Upload the file CreateVpc.yaml from the GitHub repository ([https://github.com/kohbah/CCA-670-9040-PROJECT-1](https://github.com/kohbah/CCA-670-9040-PROJECT-1)).

![](RackMultipart20201028-4-1ff9g7_html_2a37cacd1eefb5ea.gif) ![](RackMultipart20201028-4-1ff9g7_html_e8916453e58c9ba2.gif) ![](RackMultipart20201028-4-1ff9g7_html_350e994a56ebd04b.png)

**5.2** Provide VPC name and availability zone name for the VPC. Proceed to the review page and click on the create button.

![](RackMultipart20201028-4-1ff9g7_html_88842e34ac7a0e35.gif) ![](RackMultipart20201028-4-1ff9g7_html_e8916453e58c9ba2.gif) ![](RackMultipart20201028-4-1ff9g7_html_919e64ab3a820f40.gif) ![](RackMultipart20201028-4-1ff9g7_html_21bb353a8125b993.png)

![](RackMultipart20201028-4-1ff9g7_html_50d47731b41fc2d2.gif) ![](RackMultipart20201028-4-1ff9g7_html_abe3fc031fddd7e5.png)

**5.3** Go to the CloudFormation console in the administrative region (us-east-1 in this example). Select the CreateVpc stack, click Actions, and select Delete Stack to delete the CreateVpc stack.

![](RackMultipart20201028-4-1ff9g7_html_154da5be101c449d.gif) ![](RackMultipart20201028-4-1ff9g7_html_a1e89105c36629f4.gif) ![](RackMultipart20201028-4-1ff9g7_html_55b329473e812c67.png)

**5.4** Deploy the updated CreateVpc2.yaml file as a stack (not a StackSet) within the administrative region (us-east-1). Use vpc2 for the name of the stack. Upload the file CreateVpc2.yaml from the GitHub repository ([https://github.com/kohbah/CCA-670-9040-PROJECT-1](https://github.com/kohbah/CCA-670-9040-PROJECT-1)).

![](RackMultipart20201028-4-1ff9g7_html_dfe3bb68bae319af.png)

![](RackMultipart20201028-4-1ff9g7_html_ef4a38de238a82c9.png)

**5.5** Delete vpc2 stack

![](RackMultipart20201028-4-1ff9g7_html_154da5be101c449d.gif) ![](RackMultipart20201028-4-1ff9g7_html_cd3d2aac384e1ae4.gif) ![](RackMultipart20201028-4-1ff9g7_html_63f5ae2beeb34b67.png)

**5.6** Deploy the vpcMappings.yaml file from the Github repository ([https://github.com/kohbah/CCA-670-9040-PROJECT-1](https://github.com/kohbah/CCA-670-9040-PROJECT-1)) to map CIDR values for two regions.

![](RackMultipart20201028-4-1ff9g7_html_cd3d2aac384e1ae4.gif) ![](RackMultipart20201028-4-1ff9g7_html_55fdef2291d920e6.gif) ![](RackMultipart20201028-4-1ff9g7_html_b71213d87f9a5635.png)

**5.6** Deploy the vpcMappings.yaml as a stackset. The file is located on the GitHub repository ([https://github.com/kohbah/CCA-670-9040-PROJECT-1](https://github.com/kohbah/CCA-670-9040-PROJECT-1)) for both regions to have VPC.

![](RackMultipart20201028-4-1ff9g7_html_55fdef2291d920e6.gif) ![](RackMultipart20201028-4-1ff9g7_html_4b515f38083c5377.png)

![](RackMultipart20201028-4-1ff9g7_html_55fdef2291d920e6.gif) ![](RackMultipart20201028-4-1ff9g7_html_9ea5b6e5831a1010.gif) ![](RackMultipart20201028-4-1ff9g7_html_5f3c625a57044483.png)

**5.7** Provide stackset name as &quot;CreateVpc&quot; and click next.

![](RackMultipart20201028-4-1ff9g7_html_55fdef2291d920e6.gif) ![](RackMultipart20201028-4-1ff9g7_html_55fdef2291d920e6.gif) ![](RackMultipart20201028-4-1ff9g7_html_a5645599158856d5.png)

**5.8** Under &quot;Configure StackSet options&quot; for permissions, select &quot;Self-service permissions.&quot; Provide admin role ARN and execution role name.

![](RackMultipart20201028-4-1ff9g7_html_55fdef2291d920e6.gif) ![](RackMultipart20201028-4-1ff9g7_html_4d83548b80b7ce27.gif) ![](RackMultipart20201028-4-1ff9g7_html_75a3b155397ce9b6.gif) ![](RackMultipart20201028-4-1ff9g7_html_f047fe101b30297c.gif) ![](RackMultipart20201028-4-1ff9g7_html_b0a05bfd20c76d20.png)

**5.9** On the Set deployment options page, choose &quot;Deploy stacks in accounts&quot; and specify your account ID.

![](RackMultipart20201028-4-1ff9g7_html_6529fe472445f456.gif) ![](RackMultipart20201028-4-1ff9g7_html_5a658d972819c3ed.gif) ![](RackMultipart20201028-4-1ff9g7_html_c4d93e8b167e3386.png)

**5.10** Under Specify regions, select both target regions (us-east-1 and us-west-2 in this example) and click Add to move the regions over to the Deployment order column. The order itself is not essential. Click Next.

![](RackMultipart20201028-4-1ff9g7_html_d5e0c47c1c5ae057.gif) ![](RackMultipart20201028-4-1ff9g7_html_15286da6d8680826.gif) ![](RackMultipart20201028-4-1ff9g7_html_624fdd0bd4921555.png)

**5.11** On the Review page, click Submit.

![](RackMultipart20201028-4-1ff9g7_html_e8916453e58c9ba2.gif) ![](RackMultipart20201028-4-1ff9g7_html_50ff8bc74b58a0aa.png)

CloudFormation will begin to create the StackSet by delivering the template to each region and building the individual CloudFormation stack in each region. It will take several minutes to deploy the StackSet.

**5.12** Verify stackset has been executed successfully through stack instances and operations.

![](RackMultipart20201028-4-1ff9g7_html_80707d996c53b7ad.gif) ![](RackMultipart20201028-4-1ff9g7_html_89edcc9e093cb349.png)

![](RackMultipart20201028-4-1ff9g7_html_1e9fc051ce5243db.gif) ![](RackMultipart20201028-4-1ff9g7_html_40d9cc59f5780318.png)

**6.** Create the LAMP StackSet

**6.1** Deploy the LampParent.yaml as a stack (not a StackSet) in the administrative region (us-east-1). The LampParent.yaml file will deploy nested stacks; the file is located on the GitHub repository ([https://github.com/kohbah/CCA-670-9040-PROJECT-1](https://github.com/kohbah/CCA-670-9040-PROJECT-1)). This file is a nested stack that contains values in the Lamp.yaml file. Provide the stack name and database root password. Click next and create the stack.

![](RackMultipart20201028-4-1ff9g7_html_377f05930c27525.gif) ![](RackMultipart20201028-4-1ff9g7_html_cfec31778a6c9b7e.gif) ![](RackMultipart20201028-4-1ff9g7_html_f002b0215414ca32.gif) ![](RackMultipart20201028-4-1ff9g7_html_d3ea2296f163cecd.png)

**6.2** Verify the parent template URL from S3 buck ([https://s3-external-1.amazonaws.com/cf-templates-x40l3p5w2l19-us-east-1/2020301KVP-LampParent.yaml](https://s3-external-1.amazonaws.com/cf-templates-x40l3p5w2l19-us-east-1/2020301KVP-LampParent.yaml))

![](RackMultipart20201028-4-1ff9g7_html_da049966139cb9b.gif) ![](RackMultipart20201028-4-1ff9g7_html_ab0d6d5ddaab41b.png)

**6.3** Acknowledge that AWS CloudFormation might create IAM resources with custom names and acknowledge that AWS CloudFormation might require the following capability: CAPABILITY\_AUTO\_EXPAND.

![](RackMultipart20201028-4-1ff9g7_html_822baf4231dd396c.gif) ![](RackMultipart20201028-4-1ff9g7_html_159dd9e62b5ddf42.gif) ![](RackMultipart20201028-4-1ff9g7_html_26baa549dbb0de04.png)

**6.4** From AWS CloudFormation console, very if the Lamparent stack has been created as well as the NESTED stack

![](RackMultipart20201028-4-1ff9g7_html_f3d9add64cdba5ef.gif) ![](RackMultipart20201028-4-1ff9g7_html_6608df63cea0b7bd.gif) ![](RackMultipart20201028-4-1ff9g7_html_811e7ed483ed3d2.png)

**6.5** Clink on the public IP address (from the Outputs section of CloudFormation) provided by the LampInstanceUrl is a hyperlink. Click on that hyperlink, and you should see the Apache test page.

![](RackMultipart20201028-4-1ff9g7_html_a7a14929ea767693.gif) ![](RackMultipart20201028-4-1ff9g7_html_58558ee5af35f395.gif) ![](RackMultipart20201028-4-1ff9g7_html_1481c99d88eb5243.png)

![](RackMultipart20201028-4-1ff9g7_html_ebe8e976702b8b6a.png)

**6.6** Delete the LampParent stack (not the nested stack). The nested stack will automatically be deleted after deleting the LampParent stack. Wait for the deletion of both stacks to complete.

![](RackMultipart20201028-4-1ff9g7_html_48189c29af5d9958.gif) ![](RackMultipart20201028-4-1ff9g7_html_4a20ff0effdb3603.gif) ![](RackMultipart20201028-4-1ff9g7_html_cc02b51c4fe4549c.png)

**6.7** Deploy the LampParentFinal.yaml as StackSet. The LampParentFinal.yaml file will deploy a stackset; it is located on the GitHub repository ([https://github.com/kohbah/CCA-670-9040-PROJECT-1](https://github.com/kohbah/CCA-670-9040-PROJECT-1)). This file is a nested stack that contains values in the LampParentFinal.yaml file. This stack will create a lambda role and a lambda function that will output database credentials for both regions. Under Choose a template, Select &quot;Template is ready&quot; and upload the file LampParentFinal.yaml from the GitHub repository ([https://github.com/kohbah/CCA-670-9040-PROJECT-1](https://github.com/kohbah/CCA-670-9040-PROJECT-1)).

![](RackMultipart20201028-4-1ff9g7_html_7326bdbd16253c97.gif) ![](RackMultipart20201028-4-1ff9g7_html_ad26cc7173edc5ad.gif) ![](RackMultipart20201028-4-1ff9g7_html_cd9921ddcdb1131a.png)

**6.8** Under &quot;Specify StackSet details,&quot; provide the stackset name as LampParentFinal. Click on &quot;Next.&quot;

![](RackMultipart20201028-4-1ff9g7_html_d78d5b50711093f5.gif) ![](RackMultipart20201028-4-1ff9g7_html_35eb8f2389380004.gif) ![](RackMultipart20201028-4-1ff9g7_html_a94d1f92053487ba.png)

**6.9** Under &quot;Configure StackSet options&quot; for permissions, select &quot;Self-service permissions.&quot; Provide admin role ARN and execution role name.

![](RackMultipart20201028-4-1ff9g7_html_3f650feac3e96cd7.gif) ![](RackMultipart20201028-4-1ff9g7_html_4d83548b80b7ce27.gif) ![](RackMultipart20201028-4-1ff9g7_html_75a3b155397ce9b6.gif) ![](RackMultipart20201028-4-1ff9g7_html_f047fe101b30297c.gif) ![](RackMultipart20201028-4-1ff9g7_html_b0a05bfd20c76d20.png)

**6.10** On the Set deployment options page, choose &quot;Deploy stacks in accounts&quot; and specify your account ID.

![](RackMultipart20201028-4-1ff9g7_html_6529fe472445f456.gif) ![](RackMultipart20201028-4-1ff9g7_html_5a658d972819c3ed.gif) ![](RackMultipart20201028-4-1ff9g7_html_c4d93e8b167e3386.png)

**6.11** Under Specify regions, select both target regions (us-east-1 and us-west-2 in this example) and click Add to move the regions over to the Deployment order column. The order itself is not essential. Click Next.

![](RackMultipart20201028-4-1ff9g7_html_d5e0c47c1c5ae057.gif) ![](RackMultipart20201028-4-1ff9g7_html_15286da6d8680826.gif) ![](RackMultipart20201028-4-1ff9g7_html_624fdd0bd4921555.png)

**6.12** Acknowledge that AWS CloudFormation might create IAM resources with custom names and acknowledge that AWS CloudFormation might require the following capability: CAPABILITY\_AUTO\_EXPAND.

![](RackMultipart20201028-4-1ff9g7_html_822baf4231dd396c.gif) ![](RackMultipart20201028-4-1ff9g7_html_159dd9e62b5ddf42.gif) ![](RackMultipart20201028-4-1ff9g7_html_26baa549dbb0de04.png)

**6.13** Verify the stackset was created successfully, verify the stack instances and operations.

![](RackMultipart20201028-4-1ff9g7_html_822baf4231dd396c.gif) ![](RackMultipart20201028-4-1ff9g7_html_7f49ece9c3458995.png)

![](RackMultipart20201028-4-1ff9g7_html_ec11a97e71f91b18.png)

**6.14** Go to the CloudFormation console in both regions and look at the Output tab. You should see a different value for DbRootPassword in each region. Also, click on the LampinstanceUrl to receive a response from the apache server for each region.

- For US East (N. Virginia) us-east-1

![](RackMultipart20201028-4-1ff9g7_html_e14d47c024f81a40.gif) ![](RackMultipart20201028-4-1ff9g7_html_388a8aa0bf2381de.gif) ![](RackMultipart20201028-4-1ff9g7_html_c09cfcc3673dfb5.png)

![](RackMultipart20201028-4-1ff9g7_html_8ed5d806c05fcd63.png)

- For US West (Oregon) us-west-2

![](RackMultipart20201028-4-1ff9g7_html_388a8aa0bf2381de.gif) ![](RackMultipart20201028-4-1ff9g7_html_388a8aa0bf2381de.gif) ![](RackMultipart20201028-4-1ff9g7_html_6d243c2b00d5cfc2.gif) ![](RackMultipart20201028-4-1ff9g7_html_3b72c0e34d0adda1.png)

![](RackMultipart20201028-4-1ff9g7_html_6de671fceb41141f.png)

**7.** Clean up

**7.1** Go to the CloudFormation console in the administrative region (us-east-1 in this example) and manage all StackSet. Delete the stacks in each region and then delete the StackSet itself.

![](RackMultipart20201028-4-1ff9g7_html_6d243c2b00d5cfc2.gif) ![](RackMultipart20201028-4-1ff9g7_html_6d243c2b00d5cfc2.gif) ![](RackMultipart20201028-4-1ff9g7_html_f95fa905c9ce5ed1.gif) ![](RackMultipart20201028-4-1ff9g7_html_982fb3372b02b8cb.png)

**7.2** Under &quot;Set deployment options,&quot; provide account ID and specify all the regions being used. Click Next and Submit.

![](RackMultipart20201028-4-1ff9g7_html_2dbd3cd6f4f463b7.gif) ![](RackMultipart20201028-4-1ff9g7_html_f95fa905c9ce5ed1.gif) ![](RackMultipart20201028-4-1ff9g7_html_bc36427e448f297e.png)

![](RackMultipart20201028-4-1ff9g7_html_1d273d725ad664d1.gif) ![](RackMultipart20201028-4-1ff9g7_html_9151d02ef25c4dbb.gif) ![](RackMultipart20201028-4-1ff9g7_html_528125f68caea2bf.png)

Repeat steps 7.1 to 7.2 for all other stacksets.

**7.3** Go to S3 buckets and delete all S3 buckets created during this demo for each region.

![](RackMultipart20201028-4-1ff9g7_html_52528d4e9d7d3c59.gif) ![](RackMultipart20201028-4-1ff9g7_html_d2189fd683460740.gif) ![](RackMultipart20201028-4-1ff9g7_html_504cf844531f2e12.png)

**Cloud Orchestration and Automation Recommendations**

AWS CloudFormation is an excellent cloud orchestration tool for AWS, but it cannot be used for other Cloud services. BallotOnline should always try to avoid any vendor lock-in with AWS and using CloudFormation; it will eventually lead to that in the long run. BallotOnline should make sure its CloudFormation templates are versioned either in their AWS S3 bucket or GitHub repository. Before a task is automated into production, BallotOnline should make sure the security team validates the setup&#39;s compliances. One of the disadvantages of complete automation is that it can lead to sensitive data like passwords being exposed to those who do not have to see them. More so, before a task is fully automated, the BallotOnline team should make sure it is accompanied by a detailed README.md file or SOP for other users to use them with care per company compliance.

**Conclusion**

AWS CloudFormation is a better Cloud Orchestration tool for infrastructure environments on AWS. While this is a significant advantage for AWS resources, Cloud Orchestration can be very disadvantageous with other Cloud service providers such as AZURE, GCP, and VMware. AWS CloudFormation is only supported in AWS and can not be supported by other cloud services providers. Therefore, for some of BallotOnline services that might have a similar deployment in other cloud services providers, it will be better to take advantage of the multi-cloud benefits of terraform. BallotOnline should train its engineers to use CloudFormation and Terraform to avoid vendor lock-in with AWS CloudFormation.

reference

Amazon Elastic Container Service. (n.d.). Retrieved from https://aws.amazon.com/ecs/?whats-new-cards.sort-by=item.additionalFields.postDateTime&amp;whats-new-cards.sort-order=desc&amp;ecs-blogs.sort-by=item.additionalFields.createdDate&amp;ecs-blogs.sort-order=desc

Brandon, J. (2020, January 11). What is AWS CloudFormation? Retrieved from https://www.techradar.com/news/what-is-aws-cloudformation

DeMuro, J. P. (2019, November 18). What is cloud orchestration? Retrieved from https://www.techradar.com/news/what-is-cloud-orchestration

Introduction. (n.d.). Retrieved from https://www.terraform.io/intro/index.html

Keen, E. (2019, March 4). Automation vs. Orchestration: What&#39;s the Difference? Retrieved from https://www.burwood.com/blog-archive/automation-vs-orchestration-whats-the-difference

Kumar, S. (2020, August 31). How to use AWS OpsWorks? Retrieved from https://www.whizlabs.com/blog/aws-opsworks/

McIvor, K. (2015, October 7). DevOps tools: The beginner&#39;s guide to Chef. Retrieved from https://www.theregister.com/2015/10/07/chef\_introduction/#:%7E:text=Chef%20is%20a%20configuration%20management,Etsy%2C%20Cheezburger%2C%20and%20Indiegogo.

StackSets concepts - AWS CloudFormation. (n.d.). Retrieved from https://docs.aws.amazon.com/AWSCloudFormation/latest/UserGuide/stacksets-concepts.html

What is Ansible? (n.d.). Retrieved from https://opensource.com/resources/what-ansible

What is AWS Systems Manager? - AWS Systems Manager. (n.d.). Retrieved from https://docs.aws.amazon.com/systems-manager/latest/userguide/what-is-systems-manager.html
