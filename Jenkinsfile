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
                    
                    // Skip copying since the file is already in the correct location
                    echo "index.html is already in the correct location, no need to copy."
                    
                    // Optionally, add and commit the file to GitHub (if applicable)
                    sh '''
                    git add index.html
                    git commit -m "Add index.html to deployment folder"
                    git push origin main
                    '''
                }
            }
        }
    }
}
