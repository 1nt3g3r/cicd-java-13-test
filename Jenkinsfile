pipeline {
    agent any

    stages {
        stage('Show Java') {
            steps {
                System.out.println("Java is Here");
            }
        }
        
        stage('Launch Tests') {
            steps {
                sh './gradlew test'
            }
        }

        stage('Build JAR') {
            steps {
                sh './gradlew bootJar'
            }
        }

        stage('Archive JAR') {
            steps {
                archiveArtifacts artifacts: 'build/libs/test-app.jar', onlyIfSuccessful: true
            }
        }

        stage('Deploy Node 1') {
            steps {
                echo 'Deploy node 1'
            }
        }

        stage('Sleep 15 Seconds') {
            steps {
                script {
                    sleep 15
                }
            }
        }

        stage('Deploy Node 2') {
            steps {
                echo 'Deploy node 2'
            }
        }
    }
}

