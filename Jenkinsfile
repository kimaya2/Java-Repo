pipeline {
    agent any

    environment {
        SONAR_LOGIN = 'admin'
        SONAR_PASSWORD = 'admin'
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building...'
            }
        }
        stage('SonarQube Analysis') {
            steps {
                script {
                    sh '''
                        sonar-scanner \
                            -Dsonar.login=$SONAR_LOGIN \
                            -Dsonar.password=$SONAR_PASSWORD \
                            -Dsonar.projectKey=my_project_key \
                            -Dsonar.sources=.
                    '''
                }
            }
        }
    }
}
