pipeline {
   agent any
   tools{
      maven "3.9.1"
   }
   stages {
      stage ('Build') {
         steps {
            sh 'mvn clean package' 
            echo "Development is successful"
         }
      }
      stage ('Testing') {
         steps {
            sh 'mvn test'
            echo "Testing is successful"
         }
      }
      stage ('Production') {
         steps {
                echo 'Production is successful'
            }
      }
   }
}
