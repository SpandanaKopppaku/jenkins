pipeline {
   agent any

   environment{
        ENv_URL         = "pipeline.google.com"                    // Global variable
        SSHCRD          = credentials('SSH_CRD')
         }

   stages{
    stage('Stage one') {
        steps {

          sh '''
          echo Devops training
          echo Aws training
          echo The name of the URL is ${ENV_URL}
          
          env
          '''

        }
    }
    
    stage('Stage two') {
        environment{
            
             ENv_URL = "satge.google.com"    //stage variable

                }
        steps {

            echo "This is stage two"
            echo "The name of the URL is ${ENV_URL}"

        }
    }

    stage('Stage three') {
        steps {

            echo "This is stage three"
            sh "echo -e \\e[32m hai \\e[0m"

        }
    }

   }

}