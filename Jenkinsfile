@Library('my-shared-library-java') _
pipeline{

    agent any

    stages{

        stage('Git Checkout'){
            steps{
                script{
                    
                    gitCheckout(
                        branch: "main"
                        url: "https://github.com/Siva120589/java_app.git"
                    )
                }
            }
        }
    }


}