pipeline {
   agent {
        label 'WS'
    }
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
    
    // triggers { cron('* */1 * * *') }

   stages{
    stage('Parallel Stages') {
        parallel {
            stage('In Parallel 1') {
                steps {
                    echo "In Parallel 1"
                    sh "sleep 1"
                    sh "hostname"
                     }
                }
            stage('In Parallel 2') {
                steps {
                    echo "In Parallel 2"
                    sleep 1
                    }
                }
            stage('In Parallel 3') {
                steps {
                    echo "In Parallel 3"
                    sleep 1
                    }
                }
            }
         }
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
        // input {
        // message "Should we continue?"
        // ok "Yes, we should."
        // submitter "alice,bob"
        //     parameters {
        //         string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        //         }
        //      }       
        steps {

            echo "This is stage two"
            echo "The name of the URL is ${ENV_URL}"

        }
    }
    stage('Stage three') {
        when { 
            branch 'dev' 
            changeset "**/*.js"
             }
        steps {

            sh '''
            echo -e "\\e[32m hai"
            echo "This is stage three"
            '''
            

        }
    }
    stage('Stage four') {
        steps {

            sh '''
            echo -e "\\e[32m hai"
            echo "This is stage three"
            '''
        }
    }
// post { 
//      always { 
//          cleanWs()
//         }
//    }

    }
}  