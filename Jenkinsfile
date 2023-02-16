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
  -Dsonar.login=sqp_f7dc2bfb6d31bb87f97242393d5e7b4779b451bf '''
            }
        }
    }
}