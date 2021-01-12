# AvenBot
A Discord bot is created as a personal project to provide links and tips for games I play

Configuration:
Docker image is built after any commit to master branch via github actions

To run avenbot on host machine:
Pull docker image to host machine: docker pull mylorii/avenbot; Run docker container with: docker run -d -e TOKEN(
discord bot token) mylorii/avenbot

Usefull docker commands:

- docker build {image} . - to build docker image. Dot refers to Dockerfile path which is inside root project folder
- docker image ls - to see available images
- docker ps - to see running containers
- docker ps -a - to see all containers
- docker system prune -a - to delete all images and stopped containers

------------------------------------------------------------------------

To deploy and run on Heroku:

- create heroku app
- set GRADLE_TASK var in heroku to 'shadowJar'
- set TOKEN var in heroku to {discord bot token}
- run jar using this commands via Heroku CLI: heroku run:detached "java -jar build/libs/AvenBot-1.0-SNAPSHOT-all.jar" -a
  {app_name}

Usefull heroku commands:

- heroku ps - to see running dynos
- heroku ps:stop run.{runNumber to stop dyno}