pipeline {
    agent any

    stages {
        stage('Build stage'){
            def mavenhome= tool name: 'Maven3', type: 'maven'
                sh '{mavenhome}/bin/mvn package'
        }
        stage ('Compile Stage') {

            steps {
               
                withMaven(maven : 'maven3') {
                    sh 'mvn clean compile'
                }
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
