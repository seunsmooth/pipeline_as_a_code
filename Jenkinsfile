#!/usr/bin/env groovy

/*
Description:
This Jenkinsfile contains one 'stage', in which it performs several actions
on any Jenkins slave
*/

// need to ensure the docker tag used in the Makefile is lowercase
env.DOCKER_TAG = BUILD_TAG.toLowerCase()

node {
  // Checkout the repository branch/tag/commit which triggered this job into the
  // Jenkins node workspace
  stage('Build') {
    checkout scm

    // Run the Makefile steps
    sh 'make build-app'
  }
  stage('test') {
    checkout scm

    // Run the Makefile steps
    sh 'make test-app'
  }
  stage('deploy') {
    checkout scm

    // Run the Makefile steps
    sh 'make deploy-app'
  }
}

