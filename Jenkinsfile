pipeline {
    agent {
        node {
            label 'AGENT-1'
        }
    }
    environment { 
        My_APP_NAME= "DEV"
        DB_NAME= "DEV_APP_01"
        DB_IP= "10.0.0.1"
        DB_HOST= "DEV_APPP_01"
        
    }
     // Build 
    stages {
        stage('Checkout'){
            steps{
                script{
                    sh """
                        echo "Hello CheckOut"
                        env 
                    """
                }
            }
        }
        stage('Build'){
            steps{
                echo 'Building...'
            }
        }
        stage('Deploy'){
            steps{
                echo 'Deploy....'
            }
        }
    }
    post{
        always{
            echo 'Hello-world Pipeline job successfull -when its failed or success'
           // deleteDir()
        }
        success{
            echo 'Hello-world successfull condition'
        }
        failure{
            echo 'Hello-world failure condition'
        }
    }
}