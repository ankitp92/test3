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
                name=sh( script: 'echo basetrade-`date +%Y-%m-%d-%H-%M-%S`.tgz', returnStdout: true).trim()
                echo "${name}"
                a="[
                    {
                        "name": "basetrade",
                        "bucket": "dvc-artifactory",
                        "key": "${name}"
                    }
                ]"
                git checkout master
                echo "${a}" > README.md
                git -am "Updated basetrade version"
                git push

              }
            }
          }

    }

}
