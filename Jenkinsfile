pipeline {
    agent { node { label 'AGENT-1' } }
    options {
        timeout(time: 1, unit: 'HOURS') 
    }
    environment { 
        USER = 'MarthaDawson'
    }
    stages {
        stage('Build') {
            steps {
                echo 'Building..'
             sh '''
                ls -ltr
                pwd
                echo "hello from GitHub push webhook event"
                printenv
                '''
            }
        }
        stage('Test') {
            steps {
               echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
    post {
        always {
            echo 'I will always run whether job is sucess or not'
        }
    }
}