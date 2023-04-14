pipeline {
    agent { label 'agent1' }
   
    options {
        buildDiscarder(logRotator(daysToKeepStr: '10', numToKeepStr: '10'))
        timeout(time: 12, unit: 'HOURS')
        timestamps()
    }
    triggers {
        cron '@midnight'
    }
    stages {
        stage('Make executable') {
            steps {
                sh('chmod +x ./scripts/algorithm.sh')
            }
        }
        stage('Relative path') {
            steps {
                sh("./scripts/algorithm.sh")
            }
        }
        
    }
}
