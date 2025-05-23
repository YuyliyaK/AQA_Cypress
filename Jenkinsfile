pipeline{
    agent any

    parameters{ 
        string(name: 'SPEC', defaultValue: "cypress/e2e/2-advanced-examples/actions.cy.js", description: "Enter the script")
        choice(name: 'BROWSER', choices: ['chrome','edge','firefox'], description: "Choice the browser")
    }


    stages{
       
        stage('Testing'){
            steps{
                bat "npm ci"
                bat "npx cypress run --browser ${BROWSER} --spec ${SPEC}"
            }
            post {
                always {
                    allure includeProperties:
                     false,
                     jdk: '',
                     results: [[path: 'build/allure-results']]
                }
            }
        }
        stage('Deploing'){
            steps{
                echo "I haven't any deploy)"
            }
        }
    }
    
}

