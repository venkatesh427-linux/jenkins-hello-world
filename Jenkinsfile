pipeline {
    agent any

    tools {
        // Use Java JDK 21 and Maven
        jdk 'jdk21'           // Make sure this name matches Jenkins Global Tool Configuration
        maven 'M3911'         // Your configured Maven version
    }

    environment {
        JAVA_HOME = tool(name: 'jdk21', type: 'jdk')
        PATH = "${JAVA_HOME}/bin:${env.PATH}"
    }

    stages {
        stage('Echo Version') {
            steps {
                sh 'echo Print Maven and Java Versions'
                sh 'mvn -version'
                sh 'java -version'
            }
        }

        stage('Build') {
            steps {
                sh 'echo Building Project...'
                sh 'mvn clean package -DskipTests=true'
            }
        }

        stage('Unit Test') {
            steps {
                script {
                    echo "Waiting 60 seconds before running tests..."
                    for (int i = 0; i < 60; i++) {
                        echo "${i + 1}"
                        sleep 1
                    }
                    echo "Running Unit Tests..."
                    sh 'mvn test'
                }
            }
        }
    }
}
