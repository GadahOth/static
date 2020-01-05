pipeline {
    agent any
    stages {
        stage('Upload to AWS'){
            steps {
                sh 'uploading index.html to gadahjenkinsbucket'
                // withAWS(region:'us-west-2') {
                //     // do something
                // }
                withAWS(credentials:'jenkins') {
                    s3Upload(file:'index.html', bucket:'gadahjenkinsbucket')
                }
                sh '''
                    echo "successfuly uploaded!"
                '''
            }
        }
    }
}
