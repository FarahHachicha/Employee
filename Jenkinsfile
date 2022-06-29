pipeline {
         agent any
         stages{
              
               stage('Build Back') {
                    
                   steps{
                     sh 'mvn -f employeemanagerback/pom.xml compile'
                   }
                 
                 }
                  stage ('Unit Test'){
                           
                           steps {
                                    sh 'mvn -f employeemanagerback test'
                           }
                           post {
                                    always {
                                             junit 'employeemanagerback/target/surefire-reports/TEST-*.xml'
                                    }
                           }
                  }
                  stage ('Integration Test'){
                           steps {
                                    sh 'mvn -f employeemanagerback verify -Dsurefire.skip=true'

                           }
                            post {
                                    always {
                                             junit 'employeemanagerback/target/failsafe-reports/TEST-*.xml'
                                    }
                           }
                  }
                           
                           
                  }   
                
              
}
