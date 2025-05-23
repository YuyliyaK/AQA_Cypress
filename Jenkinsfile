pipeline{
    agent any

    parameters{
        string(name: 'SPEC', defaultValue: "cypress/e2e/**/**/*", description: "Enter the script")
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
                bat "npm i"
                bat "npm install --save-dev mocha-allure-reporter allure-commandline"
                bat "npm run browser:chrome"
                bat "npm run report:allure  "
            }
        }
        stage('Deploing'){
            steps{
                echo "I haven't any deploy)"
            }
        }
    }
    
}

