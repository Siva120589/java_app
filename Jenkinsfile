@Library('my-shared-library-java') _

pipeline{

    agent any

    parameters{

        choice(name: 'action', choices: 'create\ndelete', description: 'Choose create/Destroy')
    }

    stages{

        stage('Git Checkout'){

            when { expression { params.action == 'create'} }
            
            steps{
            gitCheckout(
                branch: "main",
                url: "https://github.com/Siva120589/java_app.git"
            )
            }
        }


        // stage('Unit Test maven'){

        //     when { expression { params.action == 'create'} }
            
        //     steps{
        //         script{

        //            mvnTest() 
        //         }
        //     }
        // }

        // stage('Integration Test maven'){

        //     when { expression { params.action == 'create'} }
            
        //     steps{
        //         script{

        //            mvnIntegrationTest() 
        //         }
        //     }
        // }


        // stage('Static code analysis: Sonarqube'){

        //     when { expression { params.action == 'create'} }
            
        //         steps{
        //             script{
        //             def SonarQubecredentialId = 'sonar-api'
        //             staticCodeAnalysis(SonarQubecredentialId) 
        //             }
        //         }
        // }


        // stage('Quality Gate Status Check : Sonarqube'){

        //     when { expression { params.action == 'create'} }
            
        //         steps{
        //             script{
        //             def SonarQubecredentialId = 'sonar-api'
        //             QualityGateStatus(SonarQubecredentialId) 
        //             }
        //         }
        // }

        stage('Maven Build : maven'){

            when { expression { params.action == 'create'} }
            
            steps{
                script{

                   mvnBuild()
                }
            }
        }

    }
}

