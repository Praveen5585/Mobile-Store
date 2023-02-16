pipeline{
    agent any
    stages{
        stage ('checkout the code from SCM'){
            steps{
                echo 'checkout the code'
            }
        }
        stage ('Build the project'){
            steps{
                echo 'building the project'
                sh 'mvn clean install -DskipTests'
            }
        }
        stage('sonarqube'){
            steps{
                echo'Sonar Codequality'
                sh '''
                mvn clean verify sonar:sonar \
                  -Dsonar.projectKey=Mobilestrore \
                  -Dsonar.host.url=http://20.214.165.99:9000 \
                  -Dsonar.login=sqp_a3ad1abb98c8b9c84dcc4f7732222583789ffe8e
                     '''
            }
        }
         stage ('buiding the docker image'){
             steps{
                echo 'Docker image Build'
                sh 'docker build -t mobilestore .'
        }
        }
    }
}
