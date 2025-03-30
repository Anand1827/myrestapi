pipeline {
    agent any

    tools {
        gradle 'gradle' // Ensure that Gradle is available from Jenkins' Global Tool Configuration
    }

    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/Anand1827/myrestapi.git'
            }
        }

        stage('Build') {
            steps {
                script {
                    // Run Gradle build using the wrapper script if available
                    sh './gradlew build'
                }
            }
        }
    }
}
