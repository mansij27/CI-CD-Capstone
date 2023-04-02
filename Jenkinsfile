pipeline {
   agent any
   tools{
        maven "3.9.1"
    }
   stages {
      stage ('Development') {
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
            script{
               deploy adapters: [tomcat9(credentialsId: 'TomcatCreds', path: '', url: 'http://3.26.98.133:7070/')], contextPath: null, onFailure: false, war: '**/*.war'
               echo 'Production is successful'
            }
         }
      }
   }
      post{
         success{
            mail to: 'mansi.jain1@knoldus.com',
            subject: 'Success',
            body: 'Build is successful'
         }
         failure{
            mail to: 'mansi.jain1@knoldus.com',
            subject: 'Failed',
            body: 'Build failed'
         }
      }
   
}
