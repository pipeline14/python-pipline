pipeline {
  agent { label 'jenkins-jenkins-slave python' }
       
  //  agent python
  stages {
    stage('build') {
      steps {
            //sh 'chmod 777 -R /usr/local/lib/python3.7'
            //sh 'pip  --no-cache-dir install -r requirements.txt --user'
            sh 'pip install --user -r requirements.txt'
      }
    }
    stage('test') {
      steps {
        sh 'python test.py'
      }
      post {
        always {
          junit 'test-reports/*.xml'
        }
      }    
    }
  }
}
