pipeline {
    agent any

    stages {
        stage('SCM') {
            steps {
               git branch: 'war', url: 'https://github.com/awspandian/demo-pro.git'
            }
        }
     	stage('Build') {
            steps {
               sh 'mvn clean'
	       sh 'mvn install'
            }
        }
	stage('Build') {
            steps {
               deploy adapters: [tomcat9(credentialsId: 'ws', path: '', url: 'http://3.110.172.84:9090/')], contextPath: 'demopipe', war: '**/*.war'
            }
        }
    }
}
