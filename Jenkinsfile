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
        stage('read the version'){
            steps{
                script{  //groovy script syntax
                    def packageJson = readJSON file: 'package.json'
                    appVersion = packageJson.version
                    echo "application version: $appVersion"
                }
            }
        }
        stage('Test') {
            steps {   //shell script syntax
                sh """
                echo 'this is to test'
                echo '$appVersion'
                """
            }
        }
        
    }

    post { 
        always { 
            echo 'I will always say Hello again!'
        // deleteDir()
        }
        success { 
            echo 'I will run when pipeline is success'
        }
        failure { 
            echo 'I will run when pipeline is failure'
        }
    }
}
