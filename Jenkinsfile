node {
    checkout scm
    stage('Build') {
        echo 'Building github....'
        sh 'cat secondFile'
    }
    stage('Test') {
        echo 'Testing github....'
        echo 'Error occurred'
        sh 'exit 1'
    }
    stage('Deploy') {
        when {
              expression {
                currentBuild.result == null || currentBuild.result == 'SUCCESS' 
              }
            }
            steps {
                echo 'Deploying gitbub....'
                
            }
        
    }
}
