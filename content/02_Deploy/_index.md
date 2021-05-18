---
title: "Deploy Cloud One File Storage Security"
chapter: true
weight: 60
pre: "<b>3. </b>"
---


# Deployment

The best way to learn is to get our hands dirty, so let’s deploy File Storage Security to our AWS account. First of all, make sure that all the requirements are meet, then:

Log in to File Storage Security, here: https://cloudone.trendmicro.com/filestorage/deployment, If you do not have an account, check the requirements page for details to get started. 

![Diagram](/images/fss-deploy-stacks.png)

Click on "Deploy" and select ```Scanner Stack and Storage Stack```, to deploy the full solution to your AWS account.

![Diagram](/images/fss-deploy-stacks-select.png)

Select the AWS region that best suit for you and click on ```Launch Stack```, this will redirect you to your AWS account in the region that you choose to deploy the stack. Make sure that you’re logged in and it has the correct permissions—you can check the details of the necessary permissions in the Requirements section.

You can validate the Cloud Formation Template by clicking in ```Review Stack```, or you can click the buttons below:

{{% button href="https://github1s.com/trendmicro/cloudone-filestorage-cloudformation-templates/blob/master/templates/FSS-All-In-One.template" %}}All in One Template{{% /button %}}
{{% button href="https://github1s.com/trendmicro/cloudone-filestorage-cloudformation-templates/blob/master/templates/FSS-Scanner-Stack.template" %}}Scanner Stack{{% /button %}}
{{% button href="https://github1s.com/trendmicro/cloudone-filestorage-cloudformation-templates/blob/master/templates/FSS-Storage-Stack.template" %}}Storage Stack{{% /button %}}
![Diagram](/images/fss-launch-stacks.png)

In the Cloud Formation page the <b>only required parameter</b> here is the <b>name of bucket</b> that you chose to be scanned, which is represented by ``` S3BucketToScan ```. It also supports differents parameters to customize your installation, like resource prefixes and optional key management servers (KMS) integration. For more details about these configurations check our <a href="https://cloudone.trendmicro.com/docs/file-storage-security/gs-deploy-all-in-one-stack/">Documentation Page</a>.
After adding the bucket name you will need to acknowledge and click on <b>"Create Stack"</b>

![Diagram](/images/cfdeploy.png)

After deploying the all-in-one stack in your AWS account, you must configure the scanner and storage stack Amazon Resource Names (ARNs) information in Trend Micro Cloud One console. The ARNs map a scanner stack to a storage stack, allowing them to be aware of each other.

Go to CloudFormation > Stacks > your all-in-one stack > Outputs tab and copy the content with these names: ```ScannerStackManagementRoleARN``` and ```StorageStackManagementRoleARN```. Next, paste the information into File Storage Security console.

![Diagram](/images/fss-arn-aws-info.png)

![Diagram](/images/fss-arn.png)

Click <b>Submit</b>. You will see a couple of success messages at the bottom.

![Diagram](/images/fss-two-stacks.png)

You have now completed the deployment of All-in-One stack :tada:, so let's test our deployment :laptop: