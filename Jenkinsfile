pipeline{
    agent any

    parameters{
        string(name: 'SPEC', defaulValue: "cypress/e2e/**/**/*", description: "Enter the script")
        choice(name: 'BROWSER', choices: ['chrome','edge','firefox'], description: "Choice the browser")
    }

    options{
        ansiColor('xterm')
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
                bat "npx cypress run --browser ${BROWSER} --spec ${SPEC}"
            }
        }
        stage('Deploing'){
            steps{
                echo "I haven't any deploy)"
            }
        }
    }
    post{
        always{
            publishHTML([allowMissing: false, alwaysLinkToLastBuild: false, keepAll: true, reportDir: 'cypress/report', reportFiles: 'index.html', reportName: 'HTML Report', reportTitles: ''])
        }
}
}

