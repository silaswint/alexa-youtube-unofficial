# alexa-youtube-unofficial

"invocationName" ist der Einstiegspunkt für die App. Zum Beispiel "Alexa, starte Youtube"

## Documentary

### Deployment
https://developer.amazon.com/de-DE/docs/alexa/smapi/ask-cli-command-reference.html#generate-lwa-tokens

first time usage:
1. npm install -g ask-cli
2. ask configure --no-browser
3. Anweisungen folgen, bei "Do you want to link your AWS account in order to host your Alexa skills?" dann "No" auswählen

create app for first time
1. "ask configure --no-browser" nochmals ausführen
   > create new profile
   > profile name: "silas"
   > url kopieren, im Browser einfügen und Authoriziation code kopieren, dann einfügen
   > Do you want to link your AWS account in order to host your Alexa skills? (Y/n) n
2. ask init
   > copy skill id from https://developer.amazon.com/alexa/console/ask
   > skill package path: ./skill-package
   > lambda code path: ./lambda
   > use AWS cloudFormation to deploy Lambda: n
   > Lambda runtime: nodejs16.x
   > Lambda handler: index.handler


deploy for AWS:
1. ask deploy

deploy for amazon self-hosted git:
1. (first time usage) ask util git-credentials-helper
2. git config credential.helper '!aws codecommit credential-helper $@'
   git config credential.UseHttpPath true
3. git push origin master

# Limitations for this repository

https://developer.amazon.com/en-US/docs/alexa/hosted-skills/alexa-hosted-skills-git-import.html#prerequisites-and-requirements