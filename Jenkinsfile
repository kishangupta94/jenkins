pipeline {
    agent any

    stages {
        stage('First Stage') {
            steps {
                sh '''
                #!/bin/bash
                kernel=$(uname -r)
                echo "KERNEL_VERSION=$kernel" > kernel.properties
                '''
            }
        }

        stage('Second Stage') {
            steps {
                script {
                    def properties = readProperties file: 'kernel.properties'
                    def kernel = properties.KERNEL_VERSION

                    // Use the kernel variable in the second stage
                    sh "echo $kernel"
                }
            }
        }
    }
}
