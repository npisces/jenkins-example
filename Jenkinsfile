pipeline {
    agent any
    tools{
        maven 'maven'
    }
    stages {
        stage ('Compile Stage') {

            steps {
                    sh 'mvn clean compile'
            }
        }

        stage ('Testing Stage') {

            steps {
                    sh 'mvn test sonar:sonar -Dsonar.login=admin -Dsonar.password=admin -Dsonar.host.url=http://34.74.251.57:9000 '
            }
        }


        stage ('Deployment Stage') {
            steps {
                    sh 'mvn deploy '
            }
        }
    }
}
