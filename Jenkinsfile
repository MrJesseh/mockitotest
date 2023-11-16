pipeline {
    agent any

    tools {
        jdk '19'
        gradle 'Gradle 8.4'
    }

    stages {
        stage('Build'){
            echo 'Building Code'
            sh './gradlew test'
        }
        stage('Test') {
            steps {
                echo 'Testing JUnit'
                sh './gradlew test'
            }
            post {
                always {
                    junit 'build/test-results/test/*/.xml'
               }
           }
        }
    }
}