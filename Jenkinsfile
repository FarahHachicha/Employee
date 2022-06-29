pipeline {
         agent any
         stages{
              
               stage('Build Back') {
                    
                   steps{
                     sh 'mvn -f employeemanagerback/pom.xml compile'
                   }
                 
                 }
                  stage ('Unit Test'){
                           agent{
                           
                           steps {
                                    sh 'mvn -f employeemanagerback test'
                           }
                  }
                  }   
                
              
}
