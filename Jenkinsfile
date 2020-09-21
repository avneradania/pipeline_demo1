pipeline {
        agent any
                stages {
                      stage('One') {
                          steps {
                              echo 'Hi, stage number 1'
                           }
                      }
                      stage('Two') {
                          steps {
                              input('Wanna proceed, Mr. Adania?')
                           }
                      }
                      stage('Three') {
                          when {
                              not {
                                    branch "avneradania"
                              } 
                           }
                           steps {
                                  echo "hello"
                           }
                       }
                       stage("four") {
                                parallel {
                                   stage('Unit Tests') {
                                      steps {
                                              echo "running unit tests"
                                      }
                                    }
                                    stage('Integration test') {
                                                    agent {
                                                            docker {
                                                                     reuseNode false
                                                                     image 'ubuntu'
                                                            }
                                                     }
                                                     steps {
                                                       echo "running integration test"
                                                     }
                                                     
                                    }
                    }
                }
            }
}
