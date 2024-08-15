pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building...'
                // Add steps to build your project if needed
            }
        }
        stage('Test') {
            steps {
                echo 'Testing...'
                // Add steps to test your project if needed
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying...'
                // Add steps to deploy your project if needed
            }
        }
        stage('Add index.html') {
            steps {
                script {
                    // Define the path to your index.html file relative to the Jenkins workspace
                    def indexFile = 'index.html'
                    
                    // Ensure the file is available in the workspace
                    sh "ls -l ${indexFile}"
                    
                    // Example deployment command (adjust as needed for your setup)
                    sh "cp ${indexFile} /path/to/your/deployment/folder/"
                    
                    // Optionally, add and commit the file to GitHub (if applicable)
                    sh '''
                    cd /path/to/your/deployment/folder/
                    git add index.html
                    git commit -m "Add index.html to deployment folder"
                    git push origin main
                    '''
                }
            }
        }
    }
}
