pipeline {
    agent {
        node {
            label "alpine:jdk8-mvn-3.5"
        }
    }
    options {
        skipDefaultCheckout()
    }
    stages {
        stage("Checkout...") {
            steps {
                script {
                    //checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [[$class: 'CloneOption', depth: 2, noTags: true, reference: '', shallow: false]], submoduleCfg: [], userRemoteConfigs: [[credentialsId: '7ffc18db-78bd-40d4-b6ac-6c159f6e41cb', url: 'https://github.com/steve-todorov/test-jenkins-checkouts']]])
                    def t = checkout([$class: 'GitSCM', branches: [[name: '*/master']], doGenerateSubmoduleConfigurations: false, extensions: [[$class: 'PathRestriction', excludedRegions: 'main/exclude/**', includedRegions: 'main/include/**']], submoduleCfg: [], userRemoteConfigs: [[credentialsId: '7ffc18db-78bd-40d4-b6ac-6c159f6e41cb', url: 'https://github.com/steve-todorov/test-jenkins-checkouts']]])
                    echo "t is: ${t}"
                    if(t) {
                        echo "t is true"
                    } else {
                        echo "t is false"
                    }
                }
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
