pipeline {
    agent any 
    parameters {
          string(name: 'NAME', defaultValue: 'Steffi', description: 'type name')
          choice(name: 'ENV',  choices: ['dev','staging','prod'], description: 'select choice')
          booleanParam(name: 'RUN_TESTS', defaultValue: true, description: 'type bool')
    }
    stages {
        stage('RUN'){
                when { expression { params.RUN_TESTS }}
                steps{
                    echo "Running tests"
                }
        }
        stage('SKIP'){
                when { expression { ! params.RUN_TESTS }}
                steps{
                    echo "Skipping tests"
                }
        }
        
        stage('Shell commands') {
            steps{
                echo "Hello ${params.NAME}"
                echo "Pipeling deploying to ${params.ENV}"
            }
        }
    }
}
