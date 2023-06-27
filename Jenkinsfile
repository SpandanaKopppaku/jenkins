pipeline {
   agent any

   environment{
        ENv_URL         = "pipeline.google.com"                    // Global variable
        SSHCRD          = credentials('SSH_CRD')
         }
    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
         }
    triggers { cron('* */1 * * *') }

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

            sh '''
            echo -e "\\e[32m hai"
            echo "This is stage three"
            '''
            

        }
    }

   }

}