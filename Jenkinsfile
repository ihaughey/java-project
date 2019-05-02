node('linux'){
    stage('Unit Tests'){
        sh 'ant -f test.xml -v'
        junit 'reports/result.xml'
    }
    
    stage('Build'){
        sh 'ant -f build.xml -v'
    }
    
    stage('Results'){
        junit 'reports/*.xml'
    }
}
