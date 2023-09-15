// JenkinsFile
pipeline {
    agent any
    stages {
        stage('Test') {
            steps {
                echo '>>> Testing....'
            }
        }

        // stage('Clone') {
        //     steps {
        //         echo 'Clone...'
        //         git branch: 'yeong_dev', credentialsId: '4b9e6386-246b-414c-8ff2-288af986c401', url: 'https://github.com/seyoung0698/blink-app'
        //     }
        // }

        stage('Kill') {
            steps {
                echo '>>> now Playing Process Kill'
                dir('/var/lib/jenkins/workspace') {
                    sh 'pwd'
                    sh 'sudo ./pkill.sh'
                }
            }
        }

        stage('Build') {
            steps {
                echo '>>> New Project Build'
                dir('/var/lib/jenkins/workspace/Test') {
                    // some block
                    sh 'sudo npm install'
                    sh 'sudo npm run build'
                }
            }
        }
        
        stage('Deploy') {
            steps {
                echo '>>> New Project Deploy'
                dir('/var/lib/jenkins/workspace/Test') {
                sh 'sudo ./run.daemon start'
                }
            }
        }
    }
}