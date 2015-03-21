---
layout: page
title: Howto
permalink: /howto/
---

# Troubleshooting ;)

To build locally you have to add two switches

```
./gradlew clean build -x test -x generateWiremockClientStubs 
```

# Clone the GIT properties repository to your computer

Run this command (if you have sent your SSH key to Github)

```
git clone git@github.com:microhackathon-2015-03-juglodz/properties.git

```

or if you can't conect to Github via ssh

```
git clone https://github.com/microhackathon-2015-03-juglodz/properties.git

```

# Set environment variable for GIT properties

For Linux

```bash
### Configuration which should be placed on server where app is deployed
# Environment where our app is deployed, configuration will be taken from corresponding dir
export APP_ENV="prod"
# Git repository with configuration. Absolute path should be used.
export CONFIG_FOLDER="/path/to/your/checked/out/git/repository"
# For secretProd env, ENCRYPT_KEY is required.
# Use encrypt.key if you pass it as -D option when running java
export ENCRYPT_KEY="secretEncryptKey"

```

For Windows

either do it via some UI or run this command

```batch
rem ### Configuration which should be placed on server where app is deployed
rem Environment where our app is deployed, configuration will be taken from corresponding dir
@set APP_ENV="prod"
rem Git repository with configuration. Absolute path should be used.
@set CONFIG_FOLDER="C:/path/to/your/checked/out/git/repository"
rem For secretProd env, ENCRYPT_KEY is required.
rem Use encrypt.key if you pass it as -D option when running java
@set ENCRYPT_KEY="secretEncryptKey"

```

For easy microservice execution just modify the proper `/scripts/run.sh` or `/scripts/run.bat` to include the path to your git repo

# Clone your microservice and start coding!

Well, let your team pick a service and start coding. Once you commit and push,
Jenkins will build that for you and upload your JAR to nexus. Next Rundeck will
deploy your application to the apps server. 

Each of the microservices will have a predefined port at which it will listen
to requests so you don't have to worry about that.

# I have a UI based microservice - where is my readme?!

Check this out [boot-microservice-gui-readme](https://github.com/4finance/boot-microservice#boot-microservice-gui--). Just scroll to the very bottom ;)

# I have a backend based microservice - where is my readme?!

Check this out [boot-microservice-readme](https://github.com/4finance/boot-microservice)

# I have to implement a microservice with a DB - what should I do?

For a relational DB use H2 in memory.

For a NoSQL one use [Fongo](https://github.com/fakemongo/fongo) in compile scope.

# How to run my microservice locally

It's all there in the readme - [boot-microservice-readme](https://github.com/4finance/boot-microservice)

