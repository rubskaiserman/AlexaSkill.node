# AlexaSkill.nodejs

## Dependencies

- ### NodeJS (18.x)
- ### aws cli
- ### ask cli
- ### ask-sdk-core

## Config
- ### aws configure: [link to docs](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-quickstart.html)
    - You'll need a Access Key Pair linked to your AWS IAM User

- ### ask configure: [link to docs](https://developer.amazon.com/en-US/docs/alexa/smapi/ask-cli-command-reference.html) 
    - You'll need a Account on the Alexa Developer Console.
    - Remember to connect to the aws account.

## Init
- ### ask new: [link to docs](https://developer.amazon.com/en-US/docs/alexa/smapi/ask-cli-command-reference.html#new-command)
    - Build a new Alexa skill template.
    - NodeJS, Python and Java are the supported languages
    - AWS lambda is the usual choice for building easy to scale skills
    - Some more info will be required. Usually default is fine


## Deploy
- ### ask deploy [link to docs](https://developer.amazon.com/en-US/docs/alexa/smapi/ask-cli-command-reference.html#deploy-command)
    - Deploy your code and interaction model to Alexa Developer Console and AWS Lambda (if asigned as the desired backend)
    - Your IAM User need to have the Lambda and IAM needed credentials
    - The command will automatically update the needed information on the .ask/ folder.

## Local testing
- ### ask run --watch
    - Makes the lambda call the code in your machine


## Instructions
- ### Handlers code should be build in a builder function inside the 'handlers' folder.
- ### Inside index.js, the builder return should be loaded into a constant that would be indexed into the custom SkillBuilders (Alexa.SkillBuilders.custom)
- ### The code inside the middleware will be run everytime an Intent gets called. So, make sure to not run anything too heavy inside it.
- ### GLOBALS is meant to be a global variable available for all instances of the skill that means every user has access to the same version of Globals.
