pipeline {
    agent { image: docker }
    stages {
        stage ('Getting Dockerfile and building') {
            steps {
                sh 'docker build -t apictbk/alpineapic:1.0.0 git.tools.tbk.cl/projects/APITBK/repos/api-emisor-cobroqr/Dockerfile'
                }
            }
             
        stage (' Uploading Image to Artifactory'){
            steps {
                sh ' docker image tag apictbk/alpineapic:1.0.0 artifactory.tools.tbk.cl:5000/apicrepo/apictbk/alpineapic:1.0.0 '
                sh ' docker image push artifactory.tools.tbk.cl:5000/apicrepo/apictbk/alpineapic:1.0.0 '
                 
                }
            }
        }
    post {
        success {
            echo 'Operations done succesfully'
        }
        failure {
            echo 'Operations failed'
        }
    }
     
}

