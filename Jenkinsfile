pipeline {
    agent any
    stages {
        stage('Upload to AWS'){
            steps {
                sh 'uploading index.html to gadahjenkinsbucket'
                withAWS(region:'us-west-2', credentials:'jenkins') {
                    s3Upload(file:'/index.html', bucket:'gadahjenkinsbucket', path:'/')
                }
                sh '''
                    echo "successfully uploaded!"
                '''
            }
        }
    }
}
