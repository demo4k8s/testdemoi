pipeline {
    agent any
    options {
      timestamps()
      ansiColor('xterm')
      buildDiscarder(logRotator(numToKeepStr: '15'))
    }
    parameters {
        choice choices: ['UAT1', 'UAT2', 'PLM_AD_TEST3', 'FIT1','ALL'], description: 'Select an Environment type', name: 'EnvironmentType'
        choice choices: ['RBM_Weblogic', 'RBM_VPA', 'RBM_TM', 'CM','Evault_Weblogic','Evault_Backend','ALL'], description: 'Select an Component type', name: 'ComponentType'
        choice choices: ['Stop', 'Start', 'Restart', 'Status'], description: 'Select an operation type', name: 'OperationType'
    }
    stages {
        stage('Stopping Processes') {
            parallel {
                stage('Stopping FIT1 Processes') {
                    stages {
                        stage('Stopping RBM Weblogic Process') {
                            when {
                                expression { params.EnvironmentType == 'FIT1' && params.ComponentType == 'RBM_Weblogic' && params.OperationType == 'Stop' }
                            }
                            steps {
                                sh 'ansible --version'
                            }
                        }
                    }
                }
            }
        }
    }
}
