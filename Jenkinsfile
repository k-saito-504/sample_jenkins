pipeline {
    agent any
    stages {
        stage('clean'){
            steps {
                deleteDir()
            }
        }
        stage('checkout'){
            steps {
                checkout scm
            }
        }
        stage('upload file to storage') {
            steps {
                googleStorageUpload (
                    bucket: 'gs://asia-northeast1-clp-dwh-air-3ba3d227-bucket/dags',
                    credentialsId: 'clp-avex-dwh-poc',
                    pattern: 'dags_test_composer.py'
                )
            }
        }
    }
}
