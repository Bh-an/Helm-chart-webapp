properties([pipelineTriggers([githubPush()])])

pipeline {
    agent any

    environment {
        GITHUB_TOKEN_SECRET = credentials('gh-token-secret')
        GITHUB_TOKEN = "$GITHUB_TOKEN_SECRET_PSW"
    }

    stages {
    //     stage('Checkout Repo') {
    //         steps {
    //             checkout([
    //                 $class: 'GitSCM',
    //                 branches: [[name: 'main']],
    //                 userRemoteConfigs: [[
    //                     url: 'https://github.com/csye7125-fall2022-group01/helm-chart.git',
    //                     credentialsId: 'gh-token',
    //                 ]]
    //             ])
    //         }
    //     }


        
        stage('release') {
            steps {
                
        // withCredentials([[$class: 'UsernamePasswordMultiBinding', credentialsId: 'gh-token-secret', usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD']]){
        //             sh """
        //             echo pwd=$PASSWORD
        //             GITHUB_TOKEN=$PASSWORD
        //             """
        // }

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


        // stage('Checkout') {
        //     steps {
        //         script {
        //             // The below will clone your repo and will be checked out to master branch by default.
        //             git credentialsId: $GH_TOKEN, url: 'https://github.com/csye7125-fall2022-group01/helmchart.git'
        //             // Do a ls -lart to view all the files are cloned. It will be clonned. This is just for you to be sure about it.
        //             sh "ls -lart ./*" 
        //         }
        //     }
        // }

        // stage('Semantic Release Install') {
        //     steps {
        //         sh '''
        //         npm install --save-dev semantic-release
        //         npm install @semantic-release/git @semantic-release/changelog @semantic-release/exec -D
        //         npm init release-it -y
        //         '''
        //     }
        // }

        // stage("install helm"){
        //     steps{
        //         sh 'wget https://get.helm.sh/helm-v3.6.1-linux-amd64.tar.gz'
        //         sh 'ls -a'
        //         sh 'tar -xvzf helm-v3.6.1-linux-amd64.tar.gz'
        //         sh 'sudo cp linux-amd64/helm /usr/bin'
        //         sh 'helm version'
        //     }
        // }
//
        // stage('Get repo') {
        //     steps {
        //         sh '''
        //             git remote rm origin
        //             git remote add origin https://oauth2:${GH_TOKEN}@github.com/csye7125-fall2022-group01/helmchart.git
        //             git symbolic-ref HEAD refs/heads/main
        //             git pull origin main
        //         '''
        //     }
        // }
        
        // stage('Update Version') {
        //     steps {
        //             sh '''
        //             npx semantic-release --debug
        //             '''
        //     }
        // }
        //