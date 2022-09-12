pipeline {
    agent any

    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        jdk "JDK-17"
    }

    stages {
        stage('Git') {
            steps {
                // Get some code from a GitHub repository
                git 'https://github.com/jordanGridQube/Basic_Java.git'
            }

            post {
                success {
                    bat 'echo \'Successfully retrieved git\''
                }
            }
        }
        stage('Create') {
            steps {
                // Run Java on a Windows agent, use
                bat "javac CreateFile.java"
                bat "java CreateFile"
            }

            post {
                success {
                    bat 'echo "Created file"'
                }
            }
        }
        stage('Write') {
            steps {
                // Run Java on a Windows agent, use
                bat "javac WriteFile.java"
                bat "java WriteFile"
            }

            post {
                success {
                    bat 'echo "Message written to file"'
                }
            }
        }
        stage('Read') {
            steps {
                // Run Java on a Windows agent, use
                bat "javac JavaFile.java"
                bat "echo 'Message on file is:'"
                bat "java JavaFile"
            }

            post {
                success {
                    bat 'echo "End of message."'
                }
            }
        }
    }
}
