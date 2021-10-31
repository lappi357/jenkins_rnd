pipeline {
     agent any
     stages {
        stage("Build") {
            steps {
                sh "NODE_OPTIONS=--max_old_space_size=2048 npm install"
                sh "NODE_OPTIONS=--max_old_space_size=2048 npm run build"
            }
        }
        stage("Deploy") {
            steps {
                sh "rm -rf /var/www/jenkins-react-app"
                sh "cp -r ${WORKSPACE}/build/ /var/www/jenkins-react-app/"
            }
        }
    }
}