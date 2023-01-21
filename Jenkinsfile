pipeline {

    agent any

    stages {

        stage ('Initialization') {
            steps {
                sh 'echo "Starting the build"'
            }
        }
        
        stage('Semgrep') {
            agent {
                docker {
                    image "returntocorp/semgrep-agent"
                }
            }
            steps {
                 sh 'semgrep-agent --config p/ci --config p/security-audit --config p/secrets'
                // sh 'echo ${?} > /dev/null'
            }
        }

    }
}

