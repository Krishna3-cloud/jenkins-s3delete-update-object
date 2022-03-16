pipeline {
    agent any

    stages{
        stage('deploy to S3'){
            steps{
               sh 'aws s3 cp public s3://jenkinsbucket192 --recursive'
               sh 'aws s3 website s3://jenkinsbucket192/ --index-document index.html --error-document error.html'
               sh 'aws s3api put-bucket-policy --bucket getdeletebucket --policy file://policy.json'
               sh 'aws s3 cp s3://jenkinsbucket192 . --recursive'
               sh 'aws s3 rb s3://jenkinsbucket192 --force'
               
             
            }
        }
    }
    
}
