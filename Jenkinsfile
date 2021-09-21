pipeline {
  agent any
  stages {
    stage('Log Ant version info') {
      steps {
        sh 'ant -version'
      }
    }
    stage('GitHub Jenkins Ant Build') {
      steps {
        git 'https://gitlab.training.dagility.com/manojkumar_gnanasekaran/dagilityant2.git'
        sh 'ant -init'
        sh 'ant -f build.xml'
      }
    }
  }
}
/*node{
    def antVersion = 'Ant1.9.2'
    withAnt( ["ANT_HOME=${tool antVersion}"] ) {
        sh "cd ${WORKSPACE}/ANTworkspace; $ANT_HOME/bin/ant target1 target2"
    }
    withAnt(installation: 'myinstall') {
        sh 'ant -init'
        sh 'ant -f build.xml'
    }
}
withAnt(installation: 'myinstall') {
    sh 'ant -init'
    sh 'ant -f build.xml'
}
node{
    sh 'ant -init'
    sh 'ant -f build.xml'
}
pipeline{
    agent {label 'agent' }
    tools { ant 'ant' }
    stages{
        stage('checkout') {
            steps {
                 script{
                    dir("ant")
                    {
                        git "https://gitlab.training.dagility.com/manojkumar_gnanasekaran/dagilityant2.git"
                    }   
                }
            }
        }
        stage('Deploy') {
            steps {
                script {
                    sh 'ant -init'
                    sh 'ant -f build.xml'		    
                }
            }
        }
    }    
}*/

