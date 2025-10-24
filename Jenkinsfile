pipeline {
    agent any  // Run on any available Jenkins agent

    stages {
        stage('Checkout Code') {
            steps {
                // Pull code from GitHub
                git url: 'https://github.com/Maheshh123/Jenkins.git', branch: 'main'
            }
        }

        stage('Build with Maven') {
            steps {
                // Run Maven build command
                sh 'mvn clean package'
            }
        }

        stage('Archive Artifacts') {
            steps {
                // Save JAR/WAR files from target folder
                archiveArtifacts artifacts: 'target/*.jar', fingerprint: true
            }
        }
    }

    post {
        success {
            echo 'Build and Archive Successful!'
        }
        failure {
            echo 'Build Failed!'
        }
    }
}
