pipeline {

agent {
    kubernetes {
        yamlFile 'agent.yaml'
    }
}

environment {
    IMAGE_NAME = "jarojaslv/lab3:juan-rojas"
}

stages {

    stage('install') {
        steps {
            container('node') {
                sh 'npm install'
            }
        }
    }

    stage('test') {
        steps {
            container('node') {
                sh 'npm test'
            }
        }
    }

    stage('build') {
        steps {
            container('node') {
                sh 'npm run build'
            }
        }
    }

    stage('push') {
        steps {
            echo 'Imagen publicada previamente en Docker Hub'
        }
    }

    stage('deploy') {
        steps {
            container('kubectl') {
                sh 'kubectl get pods -n ns-juan-rojas'
            }
        }
    }
}

post {
    success {
        echo 'Pipeline ejecutado correctamente'
    }

    failure {
        echo 'Pipeline finalizado con errores'
    }
}


}
