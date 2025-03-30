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

        stage('Upload to Artifactory') {
            steps {
                script {
                    def server = Artifactory.server 'your-artifactory-server'
                    def uploadSpec = '''{
                        "files": [{
                            "pattern": "build/libs/*.jar",
                            "target": "myrepo/myrestapi/"
                        }]
                    }'''
                    server.upload spec: uploadSpec
                }
            }
        }

        stage('Deploy to AWS') {
            steps {
                sh 'aws s3 cp build/libs/*.jar s3://your-bucket-name/'
            }
        }
    }
}
