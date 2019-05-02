node('linux'){
    stage('Unit Tests'){
        git 'https://github.com/ihaughey/java-project.git'
        sh 'ant -f test.xml -v'
        junit 'reports/result.xml'
    }
    
    stage('Build'){
        sh 'ant -f build.xml -v'
    }
    
    stage('Deploy'){
        
    }
    
    stage('Report'){
        withCredentials([[$class: 'AmazonWebServicesCredentialsBinding', accessKeyVariable: 'AWS_ACCESS_KEY_ID', credentialsId: 'ece1ed01-b486-479a-9a59-78237bbc5ec1', secretKeyVariable: 'AWS_SECRET_ACCESS_KEY']]) {
    // some block
        sh 'aws cloudformation describe-stack-resources --region us-east-1 --stack-name jenkins'
        }
    }
}
