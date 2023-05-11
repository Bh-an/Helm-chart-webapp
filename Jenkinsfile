properties([pipelineTriggers([githubPush()])])

pipeline {
    agent any

    environment {
        GITHUB_TOKEN_SECRET = credentials('gh-token-secret')
        GITHUB_TOKEN = "$GITHUB_TOKEN_SECRET_PSW"
    }

    stages {
        stage('Checkout Repo') {
            steps {
                checkout([
                    $class: 'GitSCM',
                    branches: [[name: 'main']],
                    userRemoteConfigs: [[
                        url: 'https://github.com/csye7125-fall2022-group01/helm-chart.git',
                        credentialsId: 'gh-token',
                    ]]
                ])
            }
        }


        
        stage('release') {
            steps {
                
        sh "npm install @semantic-release/git -D"

        sh "npm install semantic-release-github -D"

        sh "npm install @semantic-release/exec -D"

        sh  "npm install semantic-release-yaml -D"

        sh "npm install semantic-release/changelog -D"

        sh  "npx semantic-release --debug"

            }

        }
    }
}
