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
                              input('Wanna proceed?')
                           }
                      }
                      stage('Three') {
                          when {
                              not {
                                    branch "master"
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
