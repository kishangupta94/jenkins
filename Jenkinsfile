pipeline {
    agent any

    stages {
        stage('First Stage') {
            steps {
                script {
                    def kernel = sh(returnStdout: true, script: 'uname -r').trim()
                    env.KERNEL_VERSION = kernel
                    echo "stage 1 completed successfully"
                }
            }
        }

        stage('Second Stage') {
            steps {
                script {
                    def kernel = env.KERNEL_VERSION

                    // Use the kernel variable in the second stage
                    sh "echo $kernel"
                    echo "stage 2 completed successfully"
                }
            }
        }
    }
}
