node('linux'){
    stage('Unit Tests'){
        ant -f test.xml -v
        reports/result.xml
    }
    
    stage('Build'){
        ant -f build.xml -v
        sh 'ant'
    }
    
    stage('Results'){
        junit 'reports/*.xml'
    }
}
