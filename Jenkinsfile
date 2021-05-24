pipeline {
    agent any
    options {
      timestamps()
      ansiColor('xterm')
      buildDiscarder(logRotator(numToKeepStr: '15'))
    }
    parameters {
        choice choices: ['Stop', 'Start', 'Restart', 'Status'], description: 'Select an operation type', name: 'OperationType'
        choice choices: ['RBM_Weblogic', 'RBM_VPA', 'RBM_TM', 'CM','Evault_Weblogic','Evault_Backend','ALL'], description: 'Select an Component type', name: 'ComponentType'
        booleanParam(name: 'FIT1', defaultValue: false, description: '')
    }
    stages {
        stage('Stopping Processes') {
            stage('Stopping FIT1 RBM Weblogic Process(Admin and Managed Server)') {
                when {
                    expression { params.OperationType == 'Stop' && params.ComponentType == 'RBM_Weblogic' && params.FIT1 }
                }
                steps {
                    sh 'git --vserion && kubectl version'
                }
            }
            stage('Stopping FIT1 RBM TM Process') {
                when {
                    expression { params.OperationType == 'Stop' && params.ComponentType == 'RBM_TM' && params.FIT1 }
                }
                steps {
                    sh 'ansible-playbook fit1_stop.yaml -t "stop_tm"'
                }
            }
            stage('Stopping FIT1 RBM VPA Process') {
                when {
                    expression { params.OperationType == 'Stop' && params.ComponentType == 'RBM_VPA' && params.FIT1 }
                }
                steps {
                    sh 'ansible-playbook fit1_stop.yaml -t "stop_vpa"'
                }
            }
            stage('Stopping FIT1 RBM CM Process') {
                when {
                    expression { params.OperationType == 'Stop' && params.ComponentType == 'RBM_CM' && params.FIT1 }
                }
                steps {
                    sh 'ansible-playbook fit1_stop.yaml -t "stop_cm"'
                }
            }
            stage('Stopping FIT1 AMM Process') {
                when {
                    expression { params.OperationType == 'Stop' && params.ComponentType == 'AMM' && params.FIT1 }
                }
                steps {
                    sh 'ansible-playbook fit1_stop.yaml -t "stop_amm"'
                }
            }
            stage('Stopping FIT1 Evault Weblogic Process') {
                when {
                    expression { params.OperationType == 'Stop' && params.ComponentType == 'Evault_Weblogic' && params.FIT1 }
                }
                steps {
                sh 'ansible-playbook fit1_stop.yaml -t "evault_stop_admin,evault_stop_ms"'
                }
            }
            stage('Stopping FIT1 Evault Backend Process') {
                when {
                    expression { params.OperationType == 'Stop' && params.ComponentType == 'Evault_Backend' && params.FIT1 }
                }
                steps {
                    sh 'ansible-playbook fit1_stop.yaml -t "stop_evault_backend"'
                }
            }
            stage('Stopping FIT1 all Processes') {
                when {
                    expression { params.OperationType == 'Stop' && params.ComponentType == 'ALL' && params.FIT1 }
                }
                steps {
                    sh 'ansible-playbook fit1_stop.yaml'
                }
            }
        }
        stage('Starting Processes') {
            stage('Starting FIT1 RBM Weblogic Process(Admin and Managed Server)') {
                when {
                    expression { params.OperationType == 'Start' && params.ComponentType == 'RBM_Weblogic' && params.FIT1 }
                }
                steps {
                    sh 'ansible-playbook fit1_start.yaml -t "rbm_start_admin,rbm_start_ms"'
                }
            }
            stage('Starting FIT1 RBM VPA Process') {
                when {
                    expression { params.OperationType == 'Start' && params.ComponentType == 'RBM_VPA' && params.FIT1 }
                }
                steps {
                    sh 'ansible-playbook fit1_start.yaml -t "start_vpa"'
                }
            }
            stage('Starting FIT1 RBM TM Process') {
                when {
                    expression { params.OperationType == 'Start' && params.ComponentType == 'RBM_TM' && params.FIT1 }
            }
                steps {
                    sh 'ansible-playbook fit1_start.yaml -t "start_tm"'
                }
            }
            stage('Starting FIT1 RBM CM Process') {
                when {
                    expression { params.OperationType == 'Start' && params.ComponentType == 'RBM_CM' && params.FIT1 }
                }
                steps {
                    sh 'ansible-playbook fit1_start.yaml -t "start_cm"'
                }
            }
            stage('Starting FIT1 AMM Process') {
                when {
                    expression { params.OperationType == 'Start' && params.ComponentType == 'AMM' && params.FIT1 }
                }
                steps {
                    sh 'ansible-playbook fit1_start.yaml -t "start_amm"'
                }
            }
            stage('Starting FIT1 Evault Weblogic Process') {
                when {
                    expression { params.OperationType == 'Start' && params.ComponentType == 'Evault_Weblogic' && params.FIT1 }
                }
                steps {
                    sh 'ansible-playbook fit1_start.yaml -t "evault_start_admin,evault_start_ms"'
                }
            }
            stage('Starting FIT1 Evault Backend Process') {
                when {
                    expression { params.OperationType == 'Start' && params.ComponentType == 'Evault_Backend' && params.FIT1 }
                }
                steps {
                    sh 'ansible-playbook fit1_start.yaml -t "start_evault_backend"'
                }
            }
            stage('Starting FIT1 all Processes') {
                when {
                    expression { params.OperationType == 'Start' && params.ComponentType == 'ALL' && params.FIT1 }
                }
                steps {
                    sh 'ansible-playbook fit1_start.yaml'
                }
            }
        }
        stage('Restarting Processes') {
            stage('Restarting FIT1 RBM Weblogic Process(Admin and Managed Server)') {
                when {
                    expression { params.OperationType == 'Restart' && params.ComponentType == 'RBM_Weblogic' && params.FIT1 }
                }
                steps {
                    sh 'git --vserion && kubectl version'
                }
            }
            stage('Restarting FIT1 RBM VPA Process') {
                when {
                    expression { params.OperationType == 'Restart' && params.ComponentType == 'RBM_VPA' && params.FIT1 }
                }
                steps {
                    sh 'ansible-playbook fit1_restart.yaml -t "restart_vpa"'
                }
            }
            stage('Restarting FIT1 RBM TM Process') {
                when {
                    expression { params.OperationType == 'Restart' && params.ComponentType == 'RBM_TM' && params.FIT1 }
                }
                steps {
                    sh 'ansible-playbook fit1_restart.yaml -t "restart_tm"'
                }
            }
            stage('Restarting FIT1 RBM CM Process') {
                when {
                    expression { params.OperationType == 'Restart' && params.ComponentType == 'RBM_CM' && params.FIT1 }
                }
                steps {
                    sh 'ansible-playbook fit1_restart.yaml -t "restart_cm"'
                }
            }
            stage('Restarting FIT1 AMM Process') {
                when {
                    expression { params.OperationType == 'Restart' && params.ComponentType == 'AMM' && params.FIT1 }
                }
                steps {
                    sh 'ansible-playbook fit1_restart.yaml -t "restart_amm"'
                }
            }
            stage('Restarting FIT1 Evault Weblogic Process') {
                when {
                    expression { params.OperationType == 'Restart' && params.ComponentType == 'Evault_Weblogic' && params.FIT1 }
                }
                steps {
                    sh 'ansible-playbook fit1_restart.yaml -t "evault_restart_admin,evault_restart_ms"'
                }
            }
            stage('Restarting FIT1 Evault Backend Process') {
                when {
                    expression { params.OperationType == 'Restart' && params.ComponentType == 'Evault_Backend' && params.FIT1 }
                }
                steps {
                    sh 'ansible-playbook fit1_restart.yaml -t "restart_evault_backend"'
                }
            }
            stage('Restarting FIT1 all Processes') {
                when {
                    expression { params.OperationType == 'Restart' && params.ComponentType == 'ALL' && params.FIT1 }
                }
                steps {
                    sh 'ansible-playbook fit1_restart.yaml'
                }
            }
        }
        stage('Checking Processes Status') {
            stage('Status of FIT1 RBM Weblogic Process(Admin and Managed Server)') {
                when {
                    expression { params.OperationType == 'Status' && params.ComponentType == 'RBM_Weblogic' && params.FIT1 }
                }
                steps {
                    sh 'ansible-playbook fit1_status.yaml -t "rbm_status_admin,rbm_status_ms"'
                }
            }
            stage('Status of FIT1 RBM VPA Process') {
                when {
                    expression { params.ComponentType == 'RBM_VPA' && params.FIT1 }
                }
                steps {
                    sh 'ansible-playbook fit1_status.yaml -t "status_vpa"'
                }
            }
            stage('Status of FIT1 RBM TM Process') {
                when {
                    expression { params.ComponentType == 'RBM_TM' && params.FIT1 }
                }
                steps {
                    sh 'ansible-playbook fit1_status.yaml -t "status_tm"'
                }
            }
            stage('Status of FIT1 RBM CM Process') {
                when {
                    expression { params.ComponentType == 'RBM_CM' && params.FIT1 }
                }
                steps {
                    sh 'ansible-playbook fit1_status.yaml -t "status_cm"'
                }
            }
            stage('Status of FIT1 AMM Process') {
                when {
                    expression { params.ComponentType == 'AMM' && params.FIT1 }
                }
                steps {
                    sh 'ansible-playbook fit1_status.yaml -t "status_amm"'
                }
            }
            stage('Status of FIT1 Evault Weblogic Process') {
                when {
                    expression { params.ComponentType == 'Evault_Weblogic' && params.FIT1 }
                }
                steps {
                    sh 'ansible-playbook fit1_status.yaml -t "evault_status_admin,evault_status_ms"'
                }
            }
            stage('Status of FIT1 Evault Backend Process') {
                when {
                    expression { params.ComponentType == 'Evault_Backend' && params.FIT1 }
                }
                steps {
                    sh 'ansible-playbook fit1_status.yaml -t "status_evault_backend"'
                }
            }
            stage('Status of FIT1 all Processes') {
                when {
                    expression { params.ComponentType == 'ALL' && params.FIT1 }
                }
                steps {
                    sh 'ansible-playbook fit1_status.yaml'
                }
            }
        }
    }
}
