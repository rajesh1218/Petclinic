pipeline {
    agent any

    stages {
        stage('Git Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/rajesh1218/Petclinic.git'
            }
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
