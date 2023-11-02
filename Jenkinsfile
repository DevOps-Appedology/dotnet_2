pipeline {
    agent any

    environment {
        GIT_REPO_URL = 'https://github.com/DevOps-Appedology/dotnet_2.git'
        WINDOWS_FOLDER = 'C:\\automatic\\Stag'
    }
//
    stages {
        stage('Checkout') {
            steps {
                script {
                    checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [], userRemoteConfigs: [[url: env.GIT_REPO_URL]]])
                }
            }
        }

# Azhar Anas Sardar
//
        stage('Copy to Windows') {
            steps {
                script {
                    // Copy built files to the Windows folder
                    def copyCmd = "xcopy /E /Y \"${env.WORKSPACE}\\*\" \"${env.WINDOWS_FOLDER}\""
                    bat script: copyCmd, returnStatus: true
                    def exitCode = powershell(returnStatus: true, script: 'exit $LASTEXITCODE')
                    if (exitCode == 0) {
                        echo "Copy to Windows folder succeeded"
                    } else {
                        error "Copy to Windows folder failed"
                    }
                }
            }
        }
    }

    post {
        success {
            echo "Build and copy to Windows folder succeeded"
        }
        failure {
            echo "Build or copy to Windows folder failed"
        }
    }
}
