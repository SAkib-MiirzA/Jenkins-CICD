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
                    // Ensure you're on the main branch to avoid detached HEAD state
                    sh 'git checkout main'

                    // Define the path to your index.html file relative to the Jenkins workspace
                    def indexFile = 'index.html'
                    
                    // Ensure the file is available in the workspace
                    sh "ls -l ${indexFile}"
                    
                    // Only add and commit if there are changes to the file
                    sh '''
                    git add index.html
                    if git diff-index --quiet HEAD --; then
                      echo "No changes to commit"
                    else
                      git commit -m "Add index.html to deployment folder"
                      git push origin main
                    fi
                    '''
                }
            }
        }
    }
}
