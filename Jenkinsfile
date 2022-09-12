pipeline {
    agent any

    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        jdk "jdk-17"
    }

    stages {
        stage('Git') {
            steps {
                // Get some code from a GitHub repository
                git branch: 'test', credentialsId: '00bf52fe-0127-40f2-9075-4c560d284b59', url: 'https://github.com/jordanGridQube/Basic_Java.git'
            }

            post {
                success {
                    echo 'Successfully retrieved git repository'
                }
            }
        }
        stage('Create') {
            steps {
                // Run Java on a Windows agent, use
                sh 'javac CreateFile.java'
                sh 'java CreateFile'
            }

            post {
                success {
                    echo "Successfully created file"
                }
            }
        }
        stage('Write') {
            steps {
                // Run Java on a Windows agent, use
                sh 'javac WriteFile.java'
                sh 'java WriteFile'
            }

            post {
                success {
                    echo "Message written to file"
                }
            }
        }
        stage('Read') {
            steps {
                // Run Java on a Windows agent, use
                sh 'javac JavaFile.java'
                echo 'Message on file is:'
                sh 'java JavaFile'
            }

            post {
                success {
                    echo "End of message."
                }
            }
        }
    }
}
