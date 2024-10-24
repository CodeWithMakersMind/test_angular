pipeline {
     agent any
     stages {
        stage("Install Dependencies") {
            steps {
                sh "sudo npm install -g @angular/cli"
                sh "sudo npm install"
            }
        }

        stage("Build") {
            steps {
                sh "sudo ng build"
            }
        }

        stage("Deploy") {
            steps {
                sh "sudo mkdir -p /var/www/angulartest.mmworkspace.com"
                sh "sudo rm -rf /var/www/angulartest.mmworkspace.com/*" // Clear previous contents
                sh "sudo cp -r ${WORKSPACE}/dist/my-app/* /var/www/angulartest.mmworkspace.com/"
                
            }
        }
    }
}
