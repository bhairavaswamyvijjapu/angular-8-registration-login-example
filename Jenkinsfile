pipeline {
    agent any
    stages {
        stage('Git SCM checkout') {
            steps {
                git credentialsId: 'Mycred', url: 'https://github.com/RiyaSriv1414/angular-8-registration-login-example.git'
            }
        }
        stage('Install dependency') {
            steps {
                bat 'npm install'
            }
        }
        stage('Run NPM Build') {
            steps {
                bat 'npm run build'
            }
        }
        stage('Upload to S3 bucket'){
            steps{
                s3Upload consoleLogLevel: 'INFO', dontSetBuildResultOnFailure: false, dontWaitForConcurrentBuildCompletion: false, entries: [[bucket: 'fairi-webportal', excludedFile: '', flatten: false, gzipFiles: true, keepForever: true, managedArtifacts: true, noUploadOnFailure: false, selectedRegion: 'us-east-1', showDirectlyInBrowser: false, sourceFile: '*/', storageClass: 'STANDARD', uploadFromSlave: false, useServerSideEncryption: true]], pluginFailureResultConstraint: 'FAILURE', profileName: 'S3 access', userMetadata: []
                }
            }
        }
    }
