---
title: "Automation and Monitoring"
chapter: true
weight: 80
pre: "<b>4. </b>"
---

# Automation and Monitoring

### Automate Actions and Monitoring your Scans

After File Storage Security completes a scan, the scan results are tagged to the file and published to Amazon SNS topic ```ScanResultTopic```.

If you want to do more with the results, you’ll have to create or add a post-scan action. We provide many samples of integrations that can be done with File Storage Security on our GitHub page. One of the most used post-scan actions is the ability to send clean files to one Amazon S3 bucket (promote) and send malicious files to another Amazon S3 bucket (quarantine). We also provide an API to help with creating your own post-scan actions  :laptop:

### Contributing

If you encounter a bug, think of a useful feature, or find something confusing in the docs, please
[create a new issue](https://github.com/trendmicro/cloudone-filestorage-plugins/issues/new)!

We :sparkling_heart: pull requests :laptop: :right_arrow: :cloud:. If you'd like to fix a bug, contribute to a feature or
just correct a typo, please feel free to do so.


#### Contribution Guidelines:

- Fork this repository.
- Commit your code with a message that is structured according to the [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0-beta.2/) specification.
- Submit a PR and request a review:  [Submit PR](https://github.com/trendmicro/cloudone-filestorage-plugins/pulls/new).

--------

Let's start creating the post-actions for automation and monitoring :rocket: