pipeline {
    agent any

    environment {
        SONAR_URL = 'http://35.238.254.160:9000/'
        SONAR_LOGIN = 'admin'
        SONAR_PASSWORD = 'kimaya'
    }

    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                git 'https://github.com/kimaya2/Java-Repo'
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
                            -Dsonar.sources=. \
                            -Dsonar.host.url=$SONAR_URL \
                            -Dsonar.projectBaseDir=/var/jenkins_home/workspace/Github-Scanner
                    '''
                }
            }
        }
    }
}
