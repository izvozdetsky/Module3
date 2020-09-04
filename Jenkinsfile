node {
    try {
        
        environment {
             registry = "izvozdetsky/Module4"
             registryCredential = 'CrossFire109'
             dockerImage = ''
        }
        agent any
        stage ('Checkout') {
            git branch: 'master', url: 'https://github.com/izvozdetsky/Module3'
        }
        stage('Building image') {
            steps{
                script {
                    dockerImage = docker.build registry
                }
            }
         }
         stage('Deploy Image') {
            steps{
                script {
                    docker.withRegistry( '', registryCredential ) {
                        dockerImage.push()
                    }
                }
            }
          }
          stage('Remove Unused docker image') {
            steps{
                 sh "docker rmi $registry:$BUILD_NUMBER"
            }
          }
    } catch(e) {
        sh 'exit 1'
        throw e    
    } 
}
