pipeline {
   agent any
   tools{
      maven "3.9.1"
    }
   stages {
      stage ('Build 2') {
         steps {
            sh 'mvn clean package' 
            echo "Development is successful"
         }
      }
      stage ('Testing 2') {
         steps {
            sh 'mvn test'
            echo "Testing is successful"
         }
      }
  
   
   }
}
