pipeline {
   agent any

   environment{
       
        ENv_URL = "pipeline.google.com"

         }

   stages{

    stage('Stage one') {
        steps {

          sh '''
          echo Devops training
          echo Aws training
          echo The name of the URL is ${ENV_URL}

          '''

        }
    }
    
    stage('Stage two') {
        environment{
            
             ENv_URL = "pipeline.google.com"    //stage variable

                }
        steps {

            echo "This is stage two"
            echo "The name of the URL is ${ENV_URL}"

        }
    }

    stage('Stage three') {
        steps {

            echo "This is stage three"

        }
    }

   }

}