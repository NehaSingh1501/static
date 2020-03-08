pipeline {
    agent any

    stages {
        stage('Linting the code using tidy') {
            steps {
                sh 'tidy -q -e *.html'
                    }
        }
        stage('Upload to AWS') {
            steps {
                sh 'echo "Hello Jenkins"'
                sh '''
                  echo "Multi step"
                '''
                 withAWS(region:'us-west-2', credentials:'static') {
                    s3Upload(file:'index.html', bucket:'udacityproject3s3bucketneha', path:'index.html')
                 }

            }
        }
    }
}



