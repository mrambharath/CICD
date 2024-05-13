pipeline {
    agent any
    
    environment {
        PATH = "/opt/apache-maven-3.9.6/bin:$PATH"
    }

    stages {
        stage('Checkout') {
            steps {
                // Checkout source code from version control (e.g., Git)
                git branch: 'main', url: 'https://github.com/mrambharath/CICD.git'
                // Or if you are using a specific branch
                // git branch: 'main', url: 'https://github.com/mrambharath/CICD.git'
            }
        }
        stage('Build') {
            steps {
                script {
                    //def mvnHome = '/root/apache-maven-3.9.6'  // Specify the path to Maven installation
                    //sh "${mvnHome}/bin/mvn clean install"
                    sh "mvn clean install"
                }
            }
        }
    }

    post {
        success {
            // If the build succeeds, perform any post-build actions here
            echo 'Build succeeded!'
        }
        failure {
            // If the build fails, perform any post-failure actions here
            echo 'Build failed!'
        }
    }
}
