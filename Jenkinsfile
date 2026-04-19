pipeline {
    agent {
        node {
            label 'AGENT-1'
        }
    }
     // Build 
    stages {
        stage('Checkout'){
            steps{
                echo 'Git clone https://git.hub.com-branchname'
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
}
    post{
        always{
            echo 'Hello-world Pipeline job successfull -when its failed or success'
            deleteDir()
        }
        success{
            echo 'Hello-world successfull condition'
        }
        failure{
            echo 'Hello-world failure condition'
        }

    }
}