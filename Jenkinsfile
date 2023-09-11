pipeline {
    agent { 
        node {
            label 'docker-agent-dotnet'
            }
      }
    triggers {
        pollSCM 'H/5 * * * *'
    }
    stages {
        stage('Build') {
            steps {
                echo "Building.."
                sh '''
                dotnet build
                '''
            }
        }
        stage('Test') {
            steps {
                echo "Testing.."
                sh '''
                dotnet run
                '''
            }
        }
        stage('Deliver') {
            steps {
                echo 'Deliver....'
                sh '''
                echo "doing delivery stuff.."
                '''
            }
        }
    }
}
