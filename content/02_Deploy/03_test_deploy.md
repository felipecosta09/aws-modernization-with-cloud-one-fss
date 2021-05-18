---
title: "Testing your Deployment"
chapter: false
weight: 70
---

### Generating your First Detection

To test your deployment, you’ll need to generate a malware detection using the eicar file. Follow the instructions below. The video below walks you through the process as well.

<video width="800" height="600" controls loop >
<source src="/images/fss_detection.mp4" type="video/mp4">
</video>


First, obtain the EICAR (European Institute for Computer Antivirus Research) file. This is a test file developed for a simple test of anti-malware engine.


In order to get the file, temporarily disable your virus scanner, otherwise it will catch the eicar file and delete it. Go to <a href="https://www.eicar.org/">EICAR</a> file page and download ```eicar_com.zip``` or any of the other versions of this file.

Upload the eicar file to your Amazon S3 bucket that you chose to be scanned by File Storage Security.

In AWS, go to Services > S3 and find your S3 bucket to scan. Next, click <b>Upload</b>. File Storage Security will scan the file, detect it as a malware, and will add tags with information about it.

You can also use the AWS Command Line Interface (CLI) to upload files. Check out this example:

``` bash
aws s3 sync eicar.txt s3://my-bucket/path
```
TFor more information on how to use the AWS CLI, check out the <a href="https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2.html">Installation</a> and <a href="https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-quickstart.html">Configuration</a> documentation

Now that you have the object uploaded to Amazon S3, you can examine the tags from the scan results. In your Amazon S3 bucket, click the file that you uploaded, then scroll to the <b>Tags</b> section, you will see the details like the example below:


![Diagram](/images/tags.png)

Look for the following tags:
``` bash
fss-scan-date "date_and_time"
fss-scan-result "malicious"
fss-scanned "true"
```
The tags indicate that File Storage Security scanned the file and tagged it correctly as malware. You have now tested your File Storage Security deployment :+1:

{{% notice note %}}
<p style='text-align: left;'>
You could do the same process with a safe file to see how File Storage Security will tag it.
</p>
{{% /notice %}}


You can also check the Scan Activity page if necessary. The scan history panel displays a bar chart of the files that have been scanned by File Storage Security. 📈

![Diagram](/images/fss-dashboard.png)


{{% notice warning %}}
<p style='text-align: left;'>
Remember to re-enable your anti-malware solution in your laptop after the test is complete.
</p>
{{% /notice %}}


