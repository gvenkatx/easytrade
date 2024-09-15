pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    // Triggering the OpenShift build
                    openshiftBuild(buildConfig: 'easytrade-app', showBuildLogs: 'true')
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    // Deploy the built image to OpenShift
                    openshiftDeploy(deploymentConfig: 'easytrade-app')
                }
            }
        }

        stage('Verify') {
            steps {
                script {
                    // Verify the deployment
                    openshiftVerifyDeployment(deploymentConfig: 'easytrade-app')
                }
            }
        }
    }
}
