pipeline {
    agent any
    stages {
        stage('Upload to AWS'){
            steps {
                sh 'uploading index.html to gadahjenkinsbucket'
                // withAWS(region:'us-west-2') {
                //     // do something
                // }
                withAWS(region:'us-west-2', credentials:'jenkins') {
                    s3Upload(file:'index.html', bucket:'gadahjenkinsbucket'), path:'path/to/target/index.html'
                }
                sh '''
                    echo "successfuly uploaded!"
                '''
            }
        }
    }
}
