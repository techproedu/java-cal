pipeline {
    agent any
    tools {
        maven 'maven'
       
    }
    
    stages {
    
        /* stage('test') {
            steps {
                script {
                    echo "test the application"
                    sh 'mvn test'
                }
            }
        }  */
        stage('build jar') {
            steps {
                script {
                    echo "building the application jar"
                    sh 'mvn package'
                }
            }
        }

        stage('build image') {
            steps {
                script {
                    echo "building the docker image"
                    sh 'docker build -t calculater .'
                    sh  'docker run -dp 80:8080 calculator'
                }
            }
        }
    }
}