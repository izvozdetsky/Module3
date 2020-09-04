node {
    try {
        deleteDir()
        stage ('Checkout') {
            git branch: 'master', url: 'https://github.com/izvozdetsky/Module3'
        }
        stage ('Build') {
            sh 'ls -la'    
        }
    } catch(e) {
        sh 'exit 1'
        throw e    
    } 
}
