# Gradle Jenkins slave

A Jenkins slave with Gradle
based on [`csanchez/jenkins-slave`](https://hub.docker.com/r/csanchez/jenkins-slave/)

A [Jenkins](https://jenkins-ci.org) slave using JNLP.

See [Jenkins Distributed builds](https://wiki.jenkins-ci.org/display/JENKINS/Distributed+builds) for more info.


## Running

To run a Docker container

    docker run aubelix/gradle-jenkins-slave -url http://jenkins-server:port <secret> <slave name>

If the command line options are not set it will try to use environment variables,
including Kubernetes set variables for services `jenkins` and `jenkins-slave`.

* `JENKINS_URL`: url for the Jenkins server
* `JENKINS_SERVICE_HOST` and `JENKINS_SERVICE_PORT`: will be used to compose the url if the previous is not present.
* `JENKINS_TUNNEL`: (`HOST:PORT`) connect to this slave host and port instead of Jenkins server
* `JENKINS_SLAVE_SERVICE_HOST` and `JENKINS_SLAVE_SERVICE_PORT`: will be used to compose the tunnel argument if the previous is not present.


# Building

    docker build -t aubele/gradle-jenkins-slave .
