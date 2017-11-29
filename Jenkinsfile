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

                sh 'printenv'
                result = sh (script: "git log -1 | grep '\\[ci skip\\]'", returnStatus: true)

                if ( result!=0 ){
                  echo $result
                  echo "Performing build"
                }else {
                  echo "Not performing build"
                }

            }
          }

    }

}
