# Build Status [![Codefresh build status]( https://g.codefresh.io/api/badges/build?repoOwner=pmpavlov&repoName=jenkins-swarm&branch=master&pipelineName=jenkins-swarm&accountName=ppavlov&type=cf-1)]( https://g.codefresh.io/repositories/pmpavlov/jenkins-swarm/builds?filter=trigger:build;branch:master;service:58eb86686aa73901008a73c9~jenkins-swarm)
# Jenkins swarm slave

[`ppavlov/jenkins-swarm`](https://hub.docker.com/r/ppavlov/jenkins-swarm/)

A [Jenkins swarm](https://wiki.jenkins-ci.org/display/JENKINS/Swarm+Plugin) slave.

For a container with ssh enabled see
[`ppavlov/jenkins-slave`](https://hub.docker.com/r/ppavlov/jenkins-slave/)

## Running

To run a Docker container passing [any parameters](https://wiki.jenkins-ci.org/display/JENKINS/Swarm+Plugin#SwarmPlugin-AvailableOptions) to the slave

    docker run ppavlov/jenkins-swarm -master http://jenkins:8080 -username jenkins -password jenkins -executors 1

Linking to the Jenkins master container there is no need to use `--master`

    docker run -d --name jenkins -p 8080:8080 ppavlov/jenkins-swarm
    docker run -d --link jenkins:jenkins ppavlov/jenkins-swarm-slave -username jenkins -password jenkins -executors 1


# Building

    docker build -t ppavlov/jenkins-swarm .
    
