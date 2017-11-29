pipeline {
    agent any


    stages {
        stage('build') {

          when {
            expression {
              return params.SKIP_PnL=="0"
            }
          }


          steps{
              script{
                name=basetrade-`date +%Y-%m-%d-%H-%M-%S`.tgz
                echo "${name}"
              }
            }
          }

    }

}
