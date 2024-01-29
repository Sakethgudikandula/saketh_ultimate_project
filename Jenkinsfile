pipeline {
    agent any 
    tools {
         maven 'maven'
         jdk 'java'
    }
    stages {
  
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
        stage('Stage-8 : Deploy to jfrog artifactory') { 
            steps {
                sh 'mvn deploy'
            }
        }
        stage('Stage-9 : Deployment - Deploy a Artifact cloudbniarydevops-3.0.0-SNAPSHOT.war file to Tomcat Server') { 
            steps {
                sh 'curl -u admin:redhat@123 -T target/**.war "http://18.212.77.252:8080/manager/text/deploy?path=/saketh&update=true"'
            }
        } 
  
        stage('Stage-10 : SmokeTest to test the functionality') { 
            steps {
                sh 'curl --retry-delay 10 --retry 5 "http://18.212.77.252:8080/devops"'
            }
        }



    }
}
