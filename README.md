# Go / AWS Lambda / Serverless Orchestration with Ansible + Vagrant

This repo provides the orchestration scripts to accompany the Badzilla blog at [Go and AWS Lambda: Web Page with API Service](http://badzilla.co.uk/go-and-aws-lambda-web-page-api-service) 

To use the repo you will need Vagrant and VirtualBox installed on your host. As usual, do:
```bash
$ vagrant up
```
## Synced Folders
Have a look at the following line in the Vagrantfile:
```bash
config.vm.synced_folder "../GoLambda/src", "/GoLambda/src"
```
This says your host lambda functions will be at the same level as this repo, but in a directory called `GoLambda/src`
Your guest directory will be at `/GoLambda/src/`. If you don't like these defaults, feel free to change them.

## Creating a New Project
Create your Serverless / AWS Lambda projects immediately below the `src` directory on your VM. For exmaple:
```bash
$ cd /GoLambda/src
$ serverless create -t aws-go-dep -p yourproject
```

## Configuring GoLand for Host / Guest VM Workflow
If you are using GoLand as your IDE on your host, there is a little configuration required to ensure that GoLand can resolve all types in the VM guest. 
Without this you will be facing a screen with many red underlines and no autocomplete. Nightmare and certain to increase 
development burden. See below as an example. 

![Unresolved types](http://badzilla.co.uk/sites/default/files/Screenshot2019-09-01at16.47.36.png)

On your host machine, install Go under your home directory and ensure the version is the same as the version on the VM. 
Then in GoLand, go to Preferences -> Go -> GOROOT and add the path as per the screenshot below.

![GOROOT](http://badzilla.co.uk/sites/default/files/Screenshot2019-09-01at16.59.10.png)

Now go to Preferences -> GO -> GOPATH and under Project GOPATH, add the path to your GoLambda directory as shown below on my host.

![GOPATH](http://badzilla.co.uk/sites/default/files/Screenshot2019-09-01at17.04.53.png)

You should now see everything resolving perfectly in your source code. Happy days! 

![Happy Days](http://badzilla.co.uk/sites/default/files/Screenshot2019-09-01at17.08.54.png)

