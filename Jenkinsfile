pipeline {
    agent any

    stages {
        
        stage ('Compile Stage') {

            steps {
               bat 'mvn clean compile'
                
            }
        }

        stage ('Testing Stage') {

            steps {
                withMaven(maven : 'maven3') {
                    sh 'mvn test'
                }
            }
        }


        stage ('Deployment Stage') {
            steps {
                withMaven(maven : 'maven3') {
                    sh 'mvn deploy'
                }
            }
        }
    }
}
