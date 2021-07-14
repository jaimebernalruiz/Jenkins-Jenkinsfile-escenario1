pipeline {
    agent { image: docker }
    stages {
        stage ('Getting Dockerfile and building') {
            steps {
                sh 'docker build -t squiroga/tbkapic:0.0.1 https://github.com/SebasQuirogaUCP/Docker-Dockerfile-Escenario1.git'
                echo 'Dockerfile (con instruacciones para clonar Repo con fuente de Golang listo)'
                echo 'Imagen Creada OK'
                }
            }
             
        stage (' Uploading Image to Dockerhub'){
            steps {
                sh ' docker login -u squiroga -p Tbk.2021.'
                echo 'Docker login OK'
                sh ' docker image push squiroga/tbkapic:0.0.1 '
                echo 'Docker image subida a DockerHub'
                 
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