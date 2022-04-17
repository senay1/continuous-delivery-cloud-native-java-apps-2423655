pipeline{
   agent any
   stages{
    stage("Build Application"){
      steps{
          sh "echo Performing Maven Build"
        }
        }

      stage("Build Conatiner image"){
        steps{
            sh "echo Build Conatiner image"
          }
          }

        stage("Publish Conatiner Image"){
          steps{

              sh "echo Publish conatiner Image"

            }
            }
}
}
