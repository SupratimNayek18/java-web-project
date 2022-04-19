pipeline{
    agent any
    stages{
        stage("BUILD"){
            steps{
                sh "mvn clean package"
            }
        }
        stage("DEPLOY"){
            steps{
                deploy adapters: [tomcat7(credentialsId: '2b34fd91-2b95-44f4-9018-393060a8a234', 
                path: '', 
                url: 'http://ec2-44-203-49-189.compute-1.amazonaws.com:8080/')], 
                contextPath: 'javawebapp', 
                war: '**/java-web-project.war'
            }
        }
    }
}
