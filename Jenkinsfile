pipeline {

    agent any

    stages {

        stage ('Initialization') {
            steps {
                sh 'echo "Starting the build"'
            }
        }
        
        stage('Semgrep') {
            steps {
                 sh "docker run -v ${WORKSPACE}:/src --workdir /src returntocorp/semgrep-agent:v1 semgrep-agent --config p/ci --config p/security-audit --config p/secrets"
                 sh "echo $? > /dev/null" 
            }
        }

    }
}

