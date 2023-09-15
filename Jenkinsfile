// JenkinsFile
pipeline {
    agent any
    stages {
        stage("Test") {
            steps {
                echo "Testing...."
            }
        }
        // stage("Clone") {
        //     steps {
        //         echo "Clone..."
        //         git branch: 'yeong_dev', credentialsId: '4b9e6386-246b-414c-8ff2-288af986c401', url: 'https://github.com/seyoung0698/blink-app'
        //     }
        // }
        stage("Build") {
            steps {
                echo "Build..."
                dir('/var/lib/jenkins/workspace/Test') {
            // some block
            sh "sudo npm install"
            sh "sudo npm run build"
            }
        }
        }
        stage("Deploy") {
            steps {
                sh "sudo npm run start"
            }
        }
    }
}