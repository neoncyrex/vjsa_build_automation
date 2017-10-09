#!groovy
 
node('jenkins') {
  stage('Checkout Source') {
    checkout scm
  }

  stage('Syntax') {
    echo 'Syntax and Lint testing'
    sh 'ls'
    sh 'ansible-lint ansible/playbooks/*.yml  ansible/playbooks/*.yaml'
    sh 'ansible-lint ansible/'
  }

  stage('Build') {
    echo "Building"
    sh "true"
  }

  stage('Deploy') {
    echo  "Deploying"
    sh "true"
  }
  stage('Test') {
    echo  "Testing"
    sh "true"
  }
  stage('Approval') {
    echo  "Please approve this change"
    input "Approve?"
    sh "true"
  }


  stage('Publish') {
    echo "publishing"
    sh "true"
  }
}
 
