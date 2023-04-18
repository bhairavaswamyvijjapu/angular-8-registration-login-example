pipeline {
    agent any
    
    environment {
        NEWRELIC_API_KEY = credentials('githubcreds')
    }
    
    stages {
        stage('Foo') {
            steps {
             sh "echo 'Hello world'"
            }
        }
       /* stage('Git SCM checkout') {
            steps {
                git credentialsId: 'Mycred', url: 'https://github.com/RiyaSriv1414/angular-8-registration-login-example.git'
            }
        }   */
        stage('Install dependency') {
            steps {
                sh 'npm install'
            }
        }
        stage('Run NPM Build') {
            steps {
                sh 'npm run build'
            }
        }
    /*    stage('Upload to S3 bucket'){
            steps{ 
             //   sh "echo 'Hi'"
                }
        }       */
       }
    }
