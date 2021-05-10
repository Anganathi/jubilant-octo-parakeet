pipeline {
   agent any
   stages{
    stage('One'){
      steps{
        echo 'Hi, this is Anganathi from Pepkor IT.'
      }
    }

    stage('Two'){
      steps{
        input('Would you like to proceed?')
      }
    }

    stage('Three'){
       when {
         not {
           branch 'main'
         }
       }
       steps{
          echo 'Hello'
      }
    }

    stage('Four'){
      parallel{
        stage('Unit Test'){
          steps{
            echo 'Running unit test...'
          }
        }
        stage('Integration Test'){
            agent {
              docker{
                reuseNode true
                image 'ubuntu'
              }
            }
            steps{
              echo 'Running the integration test...'
            }
        }
      }     
    }  
  }
}
