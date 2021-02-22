# Elastic Beanstalk with Docker (.NET 5 API)

The following template can be used to create an Elastic Beanstalk application/environment to host your API or web application through a docker container, deployed to the environment.

Note that this example references a sample container of mine, which is a .NET 5 API:

https://gallery.ecr.aws/u5s1n4m2/james-sherburn-f1-example-api

To change the container reference, please edit the `Dockerrun.aws.json` before uploading it to S3 in step 2.

- Create an S3 bucket named `elasticbeanstalk-docker-s3-bucket`.
- Add the `Dockerrun.aws.json` file to the bucket.
- Deploy the `template.yaml` file via CloudFormation.
- Wait for your environment to become ready.
- The sample API will then be available in your environment.
- If using my sample container, try hitting `/circuits/silverstone` and `/circuits/imola`.
- To force refresh your environment (after updating your docker image), use the following command:

`aws elasticbeanstalk update-environment --application-name [your_app_name] --environment-name [your_environment_name] --version-label [your_version_label]`