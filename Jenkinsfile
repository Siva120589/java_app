@Library('my-shared-library-java') _

pipeline{

    agent any

    tools {
        jdk 'jdk17'
        maven 'maven3'
    }

    stages{

        stage('Git Checkout'){
            
            steps{
            gitCheckout(
                branch: "main",
                url: "https://github.com/Siva120589/java_app.git"
            )
            }
        }


        stage('Unit Test maven'){
            
            steps{
                script{

                   mvnTest() 
                }
            }
        }

        stage('Integration Test maven'){
            
            steps{
                script{

                   mvnIntegrationTest() 
                }
            }
        }
    }
}