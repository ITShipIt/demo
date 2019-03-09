# SHIPIT - A CICD SOLUTION

AWS code configured pipeline that is able to build asynchronously with an interface for monitoring the progress. The current project uses AWS for its resources, AWS Cloudformation to build the environment, Jenkins for the pipeline, and Docker for any specific environments needed. Once Jenkins is setup from the cloudformation template, the developers will use a jenkins file to define requirements (see jenkinsFile below)and build the pipline.  

## Getting Started

Use the AWS CLI to run the CF_Pipelin.yaml template. [aws-build-template-command here]. Enter in the desired parameters (see Prerequisites).

Now use the example jenkinsFile to start a build on the pipeline.  This build will create a webserver that prints "Hello World" to the webpage.  

There will be a manual gate that will pause the pipeline so that manual testing can be done if desired.  This will send a notification to slack when arriving at this stage.  To have the pipline contiue do [insert what to do here]. 

Upon completion of the build a notification will be sent to slack with each location that the build was deployed to. 

Spot instances that were used for the builds will by default be spun down if left unused for 5 minutes.

### Prerequisites

Amazon Web Services Account with a Security Key Pair that has been generated.

CF_Pipelin.yaml -Parameters needed for initial build:

Jenkins admin username:
Default: [admin]

Jenkins admin password:
No default: [input manually]. 

SlackTeamDomain:
No default: [input manually]
  
SlackGlobalChannel:
Default: [#General]

SlackGlobalToken: (see instructions to get this token below) 
No Default: [input manually]

securityKeyPair: (see instructions to create keypair on AWS below)
No Default: [input manually]

jenkinsAdditionalPlugins: (Any additional pluggins desired that are not in the list of defaults below)
Default: []

spotInstanceType:
AllowedValues: t2.micro, t2.small, t2.medium, t2.large, t2.xlarge, t2.2xlarge, t3.nan, t3.micro, t3.small, t3.medium, t3.large, t3.xlarge, t3.2xlarge
Default: [t3.micro]

spotBidPrice: (max price that you are willing to bid for spot instance)
Default: [0.001]

spotTargetCapacity:( The target capacity of the spot fleet request).
Default: [2]

githubWebhook:
Deafault:[input manually]

```
Give examples
```

### Installing

A step by step series of examples that tell you how to get a development env running

Say what the step will be

```
Give the example
```


End with an example of getting some data out of the system or using it for a little demo

## Running the tests

Explain how to run the automated tests for this system

### Break down into end to end tests

Explain what these tests test and why

```
Give an example
```

### And coding style tests

Explain what these tests test and why

```
Give an example
```

## Deployment

Add additional notes about how to deploy this on a live system

## Built With

* [Amazon Web Services](https://aws.amazon.com/) - Cloud Computing Services
* [Jenkins](https://jenkins.io/) - A continuous integration platform with facilitating technical aspects of continuous delivery
* [Docker](https://www.docker.com/) - Application Container Platform

## Contributing

Please read [CONTRIBUTING.md](https://gist.github.com/PurpleBooth/b24679402957c63ec426) for details on our code of conduct, and the process for submitting pull requests to us.

## Versioning


## Authors

* **Cameron Bay** - *Team Lead* - [cmbay](https://github.com/cmbay)
* **Erik Pinho** - *Team Coordinator* - [epinho112](https://github.com/epinho112)
* **Trevor Garn** - *Team Member* - [Trevash](https://github.com/Trevash)
* **Charles Robinson** - *Team Member* - [crobins2121](https://github.com/crobins2121)
* **Adam Thiriot** - *Team Member* - [headlesschicken7](https://github.com/Headlesschicken7)

See also the list of [contributors](https://github.com/your/project/contributors) who participated in this project.

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details

## Acknowledgments

* Hat tip to anyone whose code was used
* Inspiration
* etc

