---
title: "Testing your Deployment"
chapter: false
weight: 70
---

### Generating your First Detection

To test your deployment, you'll need to generate a malware detection using the eicar file. Follow the instructions below. There is also a video demonstration if you prefer.

<video width="800" height="600" controls loop >
<source src="/images/fss_detection.mp4" type="video/mp4">
</video>


Obtain the EICAR file:

Temporarily disable your virus scanner, otherwise it will catch the eicar file and delete it. Go to the <a href="https://www.eicar.org/">EICAR</a> file page and download ```eicar_com.zip``` or any of the other versions of this file.

Add the eicar file to your S3 bucket:

In AWS, go to Services > S3 and find your S3 bucket to scan, click <b>Upload</b> and upload the file that you downloaded. File Storage Security will scans the file and detects as a malware.

You cna also use the AWS CLI to upload files, check this example:

``` bash
aws s3 sync eicar.txt s3://my-bucket/path
```
To know more on how to use the AWS CLI, check the <a href="https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2.html">Installation</a> and <a href="https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-quickstart.html">Configuration</a> documentation

Now you can examine the tags from the scan result, still in your S3 bucket, click in the file that you uploaded, then scroll to the <b>Tags</b> section.

![Diagram](/images/tags.png)

Look for the following tags:
``` bash
fss-scan-date date_and_time
fss-scan-result malicious
fss-scanned true
```
The tags indicate that File Storage Security scanned the file and tagged it correctly as malware. You have now tested your File Storage Security deployment :+1:

{{% notice warning %}}
<p style='text-align: left;'>
Remember to re-enable your virus scanner after testing is complete.
</p>
{{% /notice %}}


