pipeline{
   agent any

   environment{
   CONTAINER_REGISTRY = "176325/devops"
   ARTIFACT_ID = readMavenPom().getArtifactId()
   JAR_Name = "${ARTIFACT_ID)-${BUILD_NUMBER}"
   IMAGE_NAME = "${CONTAINER_REGISTRY}${ARTIFACT_ID}"
   }
   stages{
    stage("Build Application"){
        agent{
          docker
          {
            image "openjdk:11"
            reuseNode true
          }
        }
      steps{
          sh 'echo Performing Maven Build. ${ARTIFACT_ID}'
          sh './mvnw -DjarName = ${JAR_Name} clean verify'
        }
        }

      stage("Build Conatiner image"){
        steps{
            sh "echo Build Conatiner image. ${IMAGE_NAME}"
          }
          }

        stage("Publish Conatiner Image"){
          steps{

              sh "echo Publish conatiner Image"

            }
            }
}
}
