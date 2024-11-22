pipeline{
    agent any
    tools {
        maven 'm398'
    } 

    stages{
    //    stage("Running shell script"){
    //         steps{
    //             script{
    //                 for (int i =0; i<60; i++){
    //                     echo "${i+1}"
    //                     sleep i
    //                 }
    //             }
    //             }
    //     }

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