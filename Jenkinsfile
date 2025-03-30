pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/Anand1827/myrestapi.git'
            }
        }

        stage('Build') {
            steps {
                sh './gradlew build'
            }
        }
    }
}
