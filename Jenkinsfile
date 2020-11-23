pipeline {
    agent any
    stages {
        stage('checkout sourcecode')
        {
            steps {
            checkout([$class: 'GitSCM', branches: [[name: '*/example-solution']], doGenerateSubmoduleConfigurations: false, extensions: [], submoduleCfg: [], userRemoteConfigs: [[url: 'https://github.com/devops81/cicd-pipeline-train-schedule-cd.git']]])
            }
        }
        stage('Build') {
            steps {
                echo 'Running build automation'
                sh './gradlew build --no-daemon'
                archiveArtifacts artifacts: 'dist/trainSchedule.zip'
            }
        }
    }
}
