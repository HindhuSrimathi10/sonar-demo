pipeline {
    agent any

    stages {

        stage('Clone') {
            steps {
                git branch: 'main', url: 'https://github.com/HindhuSrimathi10/sonar-demo.git'
            }
        }

        stage('Build') {
            steps {
                sh 'echo "Building application..."'
            }
        }

        stage('SonarQube Analysis') {
            steps {
                withSonarQubeEnv('My Sonar Server') {
                    sh '''
                    sonar-scanner \
                    -Dsonar.projectKey=sonar-demo \
                    -Dsonar.sources=. \
                    -Dsonar.host.url=http://localhost:9000
                    '''
                }
            }
        }

    }
}
