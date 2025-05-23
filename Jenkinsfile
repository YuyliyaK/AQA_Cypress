pipeline{
    agent any

    parameters{
        string(name: 'SPEC', defaultValue: "cypress/e2e/2-advanced-examples/actions.cy.js", description: "Enter the script")
        choice(name: 'BROWSER', choices: ['chrome','edge','firefox'], description: "Choice the browser")
    }


    stages{
        stage('Building'){
            steps{
                echo "Building"
            }
        }
        stage('Testing'){
            steps{
                bat "npm ci"
                bat "npx cypress run --browser ${BROWSER} --spec ${SPEC}"
            }
        }
        stage('Deploing'){
            steps{
                echo "I haven't any deploy)"
            }
        }
    }
    
}

