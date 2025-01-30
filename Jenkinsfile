pipeline {
    agent any
    stages {
        stage('Checkout Code') {
            steps {
                git 'https://github.com/your-username/your-repo.git'
            }
        }
        stage('Run Script') {
            steps {
                sh './script.sh'
            }
        }
        stage('Send Email') {
            steps {
                emailext subject: "Jenkins Build Notification",
                        body: "Build completed successfully. Check Jenkins console output.",
                        recipientProviders: [developers(), requestor()],
                        to: 'your-email@example.com'
            }
        }
    }
}
