# sonarqube123
pipeline {
    agent any 
    
	stages {
            stage('Compile Stage') { 
                steps {
                    withMaven(maven : 'maven8593') {
		        sh 'mvn clean compile'
		}
            }
        }
        
	     stage('Test Stage') { 
                steps {
                    withMaven(maven : 'maven8593') {
		        sh 'mvn test'
	        }
            }
        }
        
	     stage('Deployment Stage') { 
                steps {
                    withMaven(maven : 'maven8593') {
		        sh 'mvn deploy'
            }
        }
    }
}
