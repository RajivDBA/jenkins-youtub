pipeline {
    agent any
    environment {
        name = 'Chintu'
    }
    parameters {
        string(name: 'person', defaultValue: 'Rajiv Ranjan', description: "Who are you?")
        booleanParam(name: 'isMale', defaultValue: true, description: "")
        choice(name: 'city', choices: ['Jaipur','Mumbai','Pune' ], description: "")        
    }
    stages {
        stage('Run a command') {
            steps {
                sh '''
                ls
                date
                pwd
                cal 2022
                '''
            }
        }
        stage('Enviorment Varialbes') {
            environment {
                username = 'RajivRanjan'
            }
            steps {
                sh 'echo  "${BUILD_ID}"'
                sh 'echo  "${name}"'
                sh 'echo  "${username}"'                
            }
        }
        stage('Parameters') {
            steps {
                echo 'Deploy on test'
                sh 'echo  "${name}"'
                sh 'echo  "${person}"'                       
            }
        }
        stage('Continue ?') {
            input {
                message "Should we continue?"
                ok "Yes we should"
            }    
            steps {
                echo 'Deploy on Prod'
            }
        }    
        stage('Deploy on Prod') {
            steps {
                echo 'Deploy on Prod'
            }
        }         
    }
    post { 
        always { 
            echo 'I will always say Hello again!'
        }
        failure { 
            echo 'failure'
        }
        success { 
            echo 'failure'
        }        
    }    
}
