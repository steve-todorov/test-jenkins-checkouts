pipeline {
    agent {
        node {
            label "alpine:jdk8-mvn-3.5"
        }
    }
    options {
        skipDefaulCheckout()
    }
    stages {
        stage("Checkout...")
        {
            script {
                def result = checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [[$class: 'PathRestriction', excludedRegions: 'main/exclude/**', includedRegions: 'main/include/**'], [$class: 'CloneOption', depth: 2, noTags: true, reference: '', shallow: false]], submoduleCfg: [], userRemoteConfigs: [[credentialsId: '7ffc18db-78bd-40d4-b6ac-6c159f6e41cb', url: 'https://github.com/steve-todorov/test-jenkins-checkouts']]])
                echo result
            }
        }
        stage("Building...") {
            steps {
                echo "Building..."
                sleep 2
            }
        }
    }
}
