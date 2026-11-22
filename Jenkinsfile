pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/Ahmed-Khalil-Abderrahim/devops-backend.git'
            }
        }
        stage('Unzip and Compile') {
            steps {
                sh '''
                    unzip -o backend.zip -d extracted_backend
                    if [ -f extracted_backend/pom.xml ]; then
                        cd extracted_backend && mvn compile
                    else
                        cd extracted_backend/backend && mvn compile
                    fi
                '''
            }
        }
    }
}
