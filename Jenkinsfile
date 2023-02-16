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
                    -Dsonar.login=sqp_d1d3cdffddda4baa7e414b7e3566e7fbba22e941
                     '''
            }
        }
    }
}