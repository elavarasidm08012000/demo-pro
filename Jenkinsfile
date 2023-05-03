pipeline {
    agent any

    stages {
        stage('SCM') {
            steps {
                git branch: 'm03', url: 'https://github.com/awspandian/demo-pro.git'
            }
        }
stage('Build'){
steps {
bat 'mvn clean'
bat 'mvn install'

}
}
stage('Deployment'){
steps {
deploy adapters: [tomcat9(credentialsId: 'web-m03', path: '', url: 'http://localhost:9090/')], contextPath: 'm03-pipe', war: '**/*.war'

}
}

    }
}

