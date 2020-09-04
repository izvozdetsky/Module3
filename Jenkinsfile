node {
    try {
        deleteDir()
        stage ('Checkout') {
            git branch: 'master', url: 'https://github.com/izvozdetsky/Module3'
        }
        stage ('Build') {
            sh 'docker build -t module3_2:1.0 -f Module3_2.env .'    
        }
    } catch(e) {
        sh 'exit 1'
        throw e    
    } 
}
