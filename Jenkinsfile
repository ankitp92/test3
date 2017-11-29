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
                a="[\n{ "name": "basetrade",\n"bucket": "dvc-artifactory",\n"key": "${name}"\n}\n]"
                echo "Here"
                git checkout master
                echo "Here"
                echo "${a}" > README.md
                echo "Here"
                git add
                echo "Here"
                git commit -m "Update"
                echo "Here"
                git push
              }
            }
          }

    }

}
