pipeline {
    agent any

    stages {
        stage('Test') {
            steps {
                echo 'Testing Email Attachment'
            }
        }
    }

    post {
        always {
            emailext(
                to: 'khattriveer2@gmail.com',
                subject: "Build ${currentBuild.currentResult}",
                body: "Build completed with status: ${currentBuild.currentResult}",
                attachLog: true,
                compressLog: true
            )
        }
    }
}
