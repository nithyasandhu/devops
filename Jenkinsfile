pipeline {
    agent any

    stages {
        stage('scm') {
            steps {
        git branch: 'main', url: 'https://github.com/nithyasandhu/devops.git2'
            }
        }
        stage('build') {
            steps {
               shell "mvn clean"
               shell "mvn install"
}
}
stage('build to images') {
            steps {
               script{
                  shell 'docker build -t nithya216/simplewebapp .'
               }
    }
}
stage('push to hub') {
            steps {
               script{
                 withDockerRegistry(credentialsId: 'Docker_cred', url: 'https://index.docker.io/v1/') {
                  shell 'docker push nithya216/simplewebapp'
               }
            }
            }
}
}
}
