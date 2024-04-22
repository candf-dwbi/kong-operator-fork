pipeline {
    options {
        timeout(time: 10, unit: 'DAYS')
        disableConcurrentBuilds()
        timestamps()
    }
    agent {
        label 'build && j11'
    }
    stages {
        stage('Build') {
            environment {
                DOCKER_REGISTRY = 'artifactory.pfizer.com/mdmhub-docker-dev'
                CHARTREPO_URL = 'https://artifactory.pfizer.com/artifactory/mdmhub-helm-dev'
            }
            steps {
                withCredentials([usernamePassword(credentialsId: 'artifactory_pfizer', passwordVariable: 'ARTIFACTORY_PASSWORD', usernameVariable: 'ARTIFACTORY_USER')]) {
                    sh 'chmod +x gradlew && ./gradlew dockerPush helmPublish'
                }
            }
        }
    }
}