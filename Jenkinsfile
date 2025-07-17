pipeline {
    agent any

    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "M3911"
    }

    stages {
        stage('Echo Version') {
            steps {
                sh 'echo Print maven Version'
                sh 'mvn -version'
            }
        }

        stage('Build') {
            steps {
                // Get some code from a GitHub repository
                // git branch: 'main', url: 'https://github.com/venkatesh427-linux/jenkins-hello-world.git'

                // Run Maven Package CMD
                sh "mvn clean package -DskipTests=true"
            }
        }

        stage('Unit Test') {
            steps {
                for (int i = 0; i < 60; i++) {
                    echo "${i + 1}"
                    sleep 1
               }
               sh "mvn test"
            }
        }
    }
}
