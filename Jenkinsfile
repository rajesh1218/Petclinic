pipeline {
    agent any

    stages {
        stage('Git Checkout') {
            steps {
                checkout scmGit(branches: [[name: '*/1.0.0.0']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/rajesh1218/Petclinic.git']])
        }
        stage('Maven Compile') {
          steps {
            // Maven compile
            sh 'mvn compile'
          }
        }
        stage('Maven Package') {
          steps {
            // Maven package
            sh 'mvn package'
          }
        }
        stage('Deploy to Tomcat') {
          steps {
            // Deploy to Tomcat
            sh 'cp target/*.war /opt/apache-tomcat-9.0.65/webapps/'
          }
        }
    }    
}
