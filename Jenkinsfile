pipeline {
    agent {
        label 'AGENT-1'
    }
    options {
        timeout(time: 1, unit: 'HOURS') 
        disableConcurrentBuilds()
        ansiColor('xterm')
    }

    stages {
        stage('Test') {
            steps {
                sh """
                echo 'this is to test'
                """
            }
        }
        
    }
}

post { 
    always { 
        echo 'I will always say Hello again!'
        deleteDir()
    }
    success { 
        echo 'I will run when pipeline is success'
    }
    failure { 
        echo 'I will run when pipeline is failure'
    }
}
