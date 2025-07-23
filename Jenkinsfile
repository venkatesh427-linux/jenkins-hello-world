pipeline {
    agent any

    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "M3911"
        jdk 'jdk21'
    }

    stages {
        stage('Echo Version') {
            steps {
                sh 'export JAVA_HOME=$JAVA_HOME && export PATH=$JAVA_HOME/bin:$PATH'
                sh 'echo Print Maven Version'
                sh 'mvn -version'
            }
        }

        stage('Build') {
            steps {
                // Clone the repository (Uncomment and configure if needed)
                // git branch: 'main', url: 'https://github.com/venkatesh427-linux/jenkins-hello-world.git'

                sh 'mvn clean package -DskipTests=true'
            }
        }

        stage('Unit Test') {
            steps {
                script {
                    for (int i = 0; i < 60; i++) {
                        echo "${i + 1}"
                        sleep 1
                    }
                    sh 'mvn test'
                }
            }
        }
    }
}
