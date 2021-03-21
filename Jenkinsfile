pipeline {
	agent any
    stages {
        stage('Build') {
            steps {
            	bat 'e:'
            	bat 'cd e:/workspace/simple-java-maven-app1@script'
                bat 'mvn -B -DskipTests clean package'
            }
        }
        stage('Test') {
            steps {
                bat 'mvn test'
            }
            post {
                always {
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }
        stage('Deliver') {
            steps {
                bat './jenkins/script/Deliver.bat'
            }
        }
    }
}
