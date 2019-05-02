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
        sh 'aws cloudformation describe-stack-resources --region us-east-1 --stack-name jenkins'
    }
}
