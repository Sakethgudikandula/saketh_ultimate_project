pipeline {
    agent any 
    tools {
         maven 'maven'
         jdk 'java'
    }
    stages {
          stage('Stage-0 : static code analysis') { 
            steps {
                sh 'mvn verify sonar:sonar'
            }
        }
        stage('Stage-1 : Clean') { 
            steps {
                sh 'mvn clean'
            }
        }
         stage('Stage-2 : Validate') { 
            steps {
                sh 'mvn validate'
            }
        }
         stage('Stage-3 : Compile') { 
            steps {
                sh 'mvn compile'
            }
        }
         stage('Stage-4 : Test') { 
            steps {
                sh 'mvn test -DskipTests'
            }
        }
          stage('Stage-5 : Package') { 
            steps {
                sh 'mvn package'
            }
        }
          stage('Stage-6 : Install') { 
            steps {
                sh 'mvn install'
            }
        }
          stage('Stage-7 : Verify') { 
            steps {
                sh 'mvn verify'
            }
        }
    }
}
