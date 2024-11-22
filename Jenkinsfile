pipeline{
    agent any
    tools {
        maven 'm398'
    }

    stages{
        stage("git checkout"){
            steps{
                git branch: 'main', url: 'https://github.com/Vineeth8686/jenkins-hello-world.git'
            }
        }

        stage("Maven Build"){
            steps{
                sh 'mvn clean package -DskipTests=true'
            }
        }

        stage("Maven Test"){
            steps{
               sh 'mvn test'
            }
        }
    }
}