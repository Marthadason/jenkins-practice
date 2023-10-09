pipeline {
    agent { node { label 'AGENT-1' } }
    options {
        timeout(time: 1, unit: 'HOURS') 
    }
    // triggers {
    //     cron('* * * * *')
    // }
    environment { 
        USER = 'MarthaDawson'
    }
    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
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
    stage('parms') {
            steps {
                echo "Hello ${params.PERSON}"

                echo "Biography: ${params.BIOGRAPHY}"

                echo "Toggle: ${params.TOGGLE}"

                echo "Choice: ${params.CHOICE}"

                echo "Password: ${params.PASSWORD}"
            }
}
