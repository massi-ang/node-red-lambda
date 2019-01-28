# Node-RED for Greengrass

This repo contains the modifications to the Node-RED code to be able to run it as a lambda inside AWS Greengrass in a docker container. 

## Setup

Download the Node-RED sources. Unzip the archive and replace the red.js file in the root folder with the one from this repo.

Run `npm install` in the root folder.

Package the content of the root folder as a zip file called `lambda.zip`. The zip file should not contain the root folder. 

Upload the lambda to AWS using the sam Cli

```
sam package --template template.yaml --bucket <bucket for code> --output-template-file deploy.yaml

sam deploy --template deploy.yaml --stack-name <a unique name>
```