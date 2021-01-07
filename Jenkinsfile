pipeline {
    agent any

    stages {
        stage('Build'){
            steps{
                sh 'mvn -B -DskipTests clean package'       
            }
        }
        stage ('Compile Stage') {

            steps {
               sh 'mvn clean compile'
                
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
