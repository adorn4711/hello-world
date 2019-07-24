node {
    checkout scm
    stage('Build') {
        echo 'Building github....'
        sh 'cat secondFile'
    }
    stage('Test') {
        echo 'Testing github....'
        echo 'Test successfull'
        sh 'exit 0'
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
