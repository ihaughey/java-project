node('linux'){
    stage('Unit Tests'){
        ant -f test.xml -v
        reports/result.xml
    }
    
    stage('Build'){
        sh 'ant'
    }
    
    stage('Results'){
        junit 'reports/*.xml'
    }
}
