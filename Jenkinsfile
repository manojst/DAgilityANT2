/*node{
    sh 'ant -init'
    sh 'ant -f build.xml'
}*/
pipeline{
    agent {label 'agent' }
    tools { ANT 'ANT' }
    stages{
        stage('checkout') {
            steps {
                 script{
                    dir("ANT")
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
}

