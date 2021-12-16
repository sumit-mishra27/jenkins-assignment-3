pipeline {
    agent {
        label 'test'
    }

    tools {
        // Install the Maven version configured as "M3" and add it to the path.
        maven "M3"
    }

    stages {
        stage('BuildinProd') {
            steps {
                // Get some code from a GitHub repository
               git branch: 'devlop', url: 'https://github.com/sumit-mishra27/jenkins-assignment-3.git'

                // Run Maven on a Unix agent.
                sh "mvn -Dmaven.test.failure.ignore=true clean package"

                // To run Maven on a Windows agent, use
                // bat "mvn -Dmaven.test.failure.ignore=true clean package"
            }
        
    }
    stage('buildInTest'){
        agent{
                label 'prod'
            }
        steps{
            
             git branch: 'prod', url: 'https://github.com/sumit-mishra27/jenkins-assignment-3.git'

                // Run Maven on a Unix agent.
                sh "mvn -Dmaven.test.failure.ignore=true clean package"

                // To run Maven on a Windows agent, use
                // bat "mvn -Dmaven.test.failure.ignore=true clean package"
        }
    }
    }
}