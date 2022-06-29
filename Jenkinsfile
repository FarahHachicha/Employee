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
                     sh './employeemanagerback/mvnw clean compile'
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
                                    sh './employeemanagerback/mvnw test'
                           }
                  }
                  }   
                
              
}
