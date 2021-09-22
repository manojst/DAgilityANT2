node {
  stage('Test') {
    //env.JAVA_HOME="${tool 'jdk_8u181'}"
    env.ANT_HOME="${tool 'ant_1_10_5'}"
    //env.PATH = "${env.JAVA_HOME}/bin:${env.ANT_HOME}/bin:${env.PATH}"
    env.PATH = "${env.ANT_HOME}/bin:${env.PATH}"
    //sh "java -version"
    //withAnt(installation: 'ant_1_10_5', jdk: 'jdk_8u181') {
    withAnt(installation: 'ant_1_10_5') {
    //  echo "Test ant"
      sh "ant -d -version"
    }
  }
}

/*node{
  //env.PATH = "${tool 'ant 1.9.7'}/bin:${env.PATH}"
  stage('GitHub Jenkins Ant Build') {
    git 'https://gitlab.training.dagility.com/manojkumar_gnanasekaran/dagilityant2.git'
    sh 'ant -version'
    sh 'ant -f build.xml'
  }
}  
def antVersion = 'Ant1.9.1'
node{
  withEnv( ["ANT_HOME=${tool antVersion}"] ) {
    sh '$ANT_HOME/bin/ant target1 target2'
  }
}
//withAnt(installation: 'LocalAnt') {
// some block
  // sh "ant build"
//for windows 
   //bat "ant build"
//}


pipeline {
  agent { docker { image 'cameronmcnz/ant-jdk8-git:latest' } }
  stages {
    stage('Log the Jenkins Docker Ant Git and Java version info') {
      steps {
        sh 'ant -version'
	    sh 'java -version'
	    sh 'git --version'
      }
    }
    stage('GitHub Jenkins Ant Docker Build') {
      steps {
        git 'https://gitlab.training.dagility.com/manojkumar_gnanasekaran/dagilityant2.git'
        sh 'ant clean compile test package war'
      }
    }
  }
}

node{
    stage ('Build and Test') {
        env.PATH = "${tool 'ant'}/bin:${env.PATH}"
        checkout scm
        sh 'ant build'
    }
    //withAnt{
    //    git 'https://gitlab.training.dagility.com/manojkumar_gnanasekaran/dagilityant2.git'
      //  sh 'ant -init'
        //sh 'ant -f build.xml'
        //sh "cd ${WORKSPACE}/ANTworkspace; $ANT_HOME/bin/ant target1 target2"
    //}
 }


def readpom;
node{
    stage('SCM Checkout'){
        
        git 'https://gitlab.training.dagility.com/manojkumar_gnanasekaran/dagilityant2.git'
    }
    stage('read POM'){
        readpom = readFile 'build.xml';
    }
    stage('Compile-Package'){
        //Get ant home path
        def antHome = tool name: 'ant', type: 'ant'
        sh "cd ${WORKSPACE}/dagilityant2; ${antHome}/bin/ant -init" 
        sh 'ant -f build.xml'       
    }
}


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
node{
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

