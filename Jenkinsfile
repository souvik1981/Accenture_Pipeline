pipeline {
    agent any
    stages {
	stage('Checkout') {
            steps {
                    git changelog: false, credentialsId: '51769ff0-0ad5-4341-8ba5-017d45d1df5c', poll: false, url: 'https://github.com/souvik1981/Accenture_Pipeline.git';
            }
        }
        stage('Compile') {
            steps {
                    bat label: '', script: 'Compile.bat';
            }
        }
        
        stage('Package') {
            steps {
                    bat label: '', script: 'Package.bat';
            }
        }
        
        stage('Deploy') {
            steps {
                    bat label: '', script: 'Deploy.bat'; 
                /*sh exit ("1");*/
            }
        }
        
               
    }
    post {
        always {
            echo 'This will always run'
        }
        success {
            echo 'This will run only if successful'
        }
        failure {
            echo 'This will run only if failed'
        }
        unstable {
            echo 'This will run only if the run was marked as unstable'
        }
        changed {
            echo 'This will run only if the state of the Pipeline has changed'
            echo 'For example, if the Pipeline was previously failing but is now successful'
        }
    }
}
