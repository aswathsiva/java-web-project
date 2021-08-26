pipeline{
    agent any
    stages{
        stage('Build'){
            steps{
                sh 'mvn clean package'
            }
        }
         stage('deploy'){
            steps{
                deploy adapters: [tomcat7(credentialsId: '75942c7f-37ef-48eb-9cfa-d8ae744130dc', path: '', 
                url: 'http://ec2-15-206-88-149.ap-south-1.compute.amazonaws.com:8080/')], 
                contextPath: 'javawebapp', war: '**/java-web-project.war'
            }
        }
    }
}
