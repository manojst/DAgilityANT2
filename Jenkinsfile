def antVersion = 'Ant1.9.2'
withAnt( ["ANT_HOME=${tool antVersion}"] ) {
    sh "cd ${WORKSPACE}/ANT2; $ANT_HOME/bin/ant target1 target2"
}
