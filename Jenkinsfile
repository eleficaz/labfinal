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
            sh 'npm install'
        }
    }

    stage('test') {
        steps {
            sh 'npm test'
        }
    }

    stage('build') {
        steps {
            sh 'npm run build'
        }
    }

    stage('push') {
        steps {
            echo 'Imagen publicada previamente en Docker Hub'
        }
    }

    stage('deploy') {
        steps {
            sh 'echo Deploy OK'
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
