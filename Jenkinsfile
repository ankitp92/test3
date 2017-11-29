pipeline {
    agent any


    stages {
        stage('build') {

          when {
            expression {
              return params.SOURCE_BRANCH=="master"
            }
          }


          steps{
              script {
                sh 'printenv'
                result = sh (script: "git log -1 | grep '[ci skip]'", returnStatus: true)
                echo "${result}"
                if ( result!=0 ){
                  echo "Performing build"
                }else {
                  echo "Not performing build"
                }
              }
            }
          }

    }

}
