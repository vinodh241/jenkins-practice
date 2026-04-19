pipeline {
    agent {
        node {
            label 'AGENT-1'
        }
    }
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