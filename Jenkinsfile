pipeline {
    agent {
        label 'master'
    }
    stages {
        stage('PRINT') {
            steps {
                bat 'echo $JOB_NAME'
            }
        }
        stage('WRITE') {
            steps {
                bat 'echo $BUILD_NUMBER >> build_number'
            }
        }
        stage('READ') {
            steps {
                bat 'cat build_number'
            }
        }
    }
    post {
        success {
            archiveArtifacts artifacts: 'build_number', fingerprint: true
        }
    }
}
