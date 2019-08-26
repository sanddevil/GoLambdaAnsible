#Go / AWS Lambda / Serverless Orchestration with Ansible + Vagrant

This repo provides the orchestration scripts to accompany the Badzilla blog at [Go and AWS Lambda: Web Page with API Service](http://badzilla.co.uk/go-and-aws-lambda-web-page-api-service) 

To use the repo you will need Vagrant and VirtualBox installed on your host. As usual, do:
```bash
$ vagrant up
```
##Synced Folders
Have a look at the following line in the Vagrantfile:
```bash
config.vm.synced_folder "../GoLambda", "/GoLambda/src"
```
This says your host lambda functions will be at the same level as this repo, but in a directory called `GoLambda`
Your guest directory will be at `/GoLambda/src/`. If you don't like these defaults, change them.