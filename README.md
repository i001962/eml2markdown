# Copy and Transform eml to markdown

Markdown eml file format using Lambda. Work in process. Expect errors and omissions.

## Deploy with CloudFormation

Prerequisites: [Node.js](https://nodejs.org/en/) and [AWS CLI](http://docs.aws.amazon.com/cli/latest/userguide/installing.html) installed

* Create an [AWS](https://aws.amazon.com/) Account and [IAM User](https://aws.amazon.com/iam/) with the `AdministratorAccess` AWS [Managed Policy](http://docs.aws.amazon.com/IAM/latest/UserGuide/access_policies_managed-vs-inline.html)
* Run `aws configure` to put store that user's credentials in `~/.aws/credentials`
* Create an S3 bucket for storing the Lambda code and store its name in a shell variable with:
  * `export CODE_BUCKET=bucket`
* Create the S3 bucket for the markdown output, store its name in shell variable:
  * `export DEST_BUCKET=bucket`
* Choose a name, but do NOT create the S3 bucket input comes from, store its name in shell variable:
  * `export SOURCE_BUCKET=bucket`
* Choose the transformation type, 1 to 25 (not yet implemented), store it in shell variable:
  * `export TRANSFORMATION=25`
* Npm install:
  * `npm install`
* Build:
  * `npm run build`
* Upload package to S3, transform the CloudFormation template:
  * `npm run package`
* Deploy to CloudFormation:
  * `npm run deploy`
* Runnow copies test file from local to S3. This will trigger lambda
  * `npm run runnow`
* Check output file to confirm transformation results
  * `npm run check`
* Cleanup before each test removes test file from S3 bucket and local drive.
  * `npm run clean`
* All in one from Build to Check output file. Only run after initial CloudFormation setup.
  * `npm run ifeallucky`        

## License
Based on &copy; 2017-2018 [Evan Chiu's](https://evanchiu.com) [serverless-galleria](https://github.com/evanchiu/serverless-galleria). This project is available under the terms of the MIT license.
