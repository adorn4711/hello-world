node {
    echo "Running ${env.BUILD_ID} on ${env.JENKINS_URL}"
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
          if (currentBuild.result == null || currentBuild.result == 'SUCCESS') { 
            echo 'deploy'
        }
 
        
    }
}
