pipeline {
    agent any
    tools {
        maven 'Maven 3.9'
        jdk 'jdk 17'
    }
    stages {
        stage('Initialize') {
            steps {
                bat '''
                    echo "PATH = ${PATH}"
                    echo "JAVA_HOME" = ${JAVA_HOME}
                    echo "MAVEN_HOME = ${MAVEN_HOME}"
                '''
            }
        }
        stage('Build') {
            steps {
                echo 'BUILD'
                bat 'mvn clean install -DskipTests=true'
            }
        }
        stage('Test') {
            steps {
                echo 'TEST'
                bat 'mvn test'
            }
        }
        stage('Package') {
            steps {
                echo 'PACKAGE'
                bat 'mvn package'
            }
        }
        stage('Deploy') {
            steps {
                echo 'DEPLOY'
            }
        }
    }
}
