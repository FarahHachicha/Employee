pipeline {
         agent any
         stages{
              
               stage('Build Back') {
                    agent {
                           docker {
                             image 'maven:3.6.0-jdk-8-alpine'
                             args '-p 80:80'
                              
                                  }
                          }
                   steps{
                     sh 'mvn -f employeemanagerback/pom.xml compile'
                   }
                 
                 }
                  stage ('Unit Test'){
                           agent{
                                    docker{
                                             image 'maven:3.6.0-jdk-8-alpine'
                                             args '-p 80:80' 
                                             reuseNode true
                                             
                                    }
                           }
                           
                           steps {
                                    sh 'mvn -f employeemanagerback/pom.xml test'
                           }
                  }
                  }   
                
              
}
