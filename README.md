## Jenkins Pipeline for Python Build and Test Stages
* Link to YouTube video overview of this process: https://youtu.be/6njM8g5hKuk
### Installation with Docker
* Install Docker on your local machine.
* Run this command: `docker run -p 8080:8080 -p 50000:50000 -v jenkins_home:/var/jenkins_home jenkins/jenkins:lts-jdk11`
* Write down the password that's created for you during this first time set up process: like `8458e513eacd41d8875ca3253f47d3a0`
* Go to `localhost:8080` and you should be prompted for this password 
* Follow the steps in this video: https://youtu.be/6njM8g5hKuk to create the pipeline 
* The link to the public Github repo that was built and tested in the video is: https://github.com/vastevenson/pytest-intro-vs
* While the docker container is running, run cmd: `docker ps` to see what containers are running - copy the container ID for Jenkins, like `8f7c957e19fd`
* Run command: `docker exec -it -u 0 8f7c957e19fd /bin/bash` to open an interactive terminal within the Docker Container as root (user 0) 
* Run command: `apt-get update` and `apt-get install python3` and `apt-get install python3-pip` to install Python3 and pip within the Docker container 
* Run `pip install pytest` to install the pytest package that actually runs the unit/integ tests during your test stage within the pipeline
