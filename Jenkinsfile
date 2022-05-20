pipeline{
    //Directives
    agent any
    tools {
        maven 'maven'
    }
     stages {
        // Specify various stage with in stages

        // stage 1. Build
        stage ('Build'){
            steps {
                sh 'mvn clean install package'
            }
        }
     

        // Stage2 : Testing
        stage ('Test'){
            steps {
                echo ' testing......'

            }
        }
     // Stage3 : Publish the artifacts to NEXUS
        stage ('Publish to Nexus'){
            steps {
                nexusArtifactUploader artifacts: [[artifactId: 'GELDevOpsLab', classifier: '', file: 'target/GELDevOpsLab-0.0.6-SNAPSHOT.war', type: 'war']], credentialsId: '7f6e0c41-f168-412d-8333-54d6827e1e5c', groupId: 'goaelectronics', nexusUrl: '172.20.10.217:8081', nexusVersion: 'nexus3', protocol: 'http', repository: 'GEL-Devopslab-SNAPSHOT', version: '0.0.6-SNAPSHOT
            }
        }

      // Stage4 : Deploying
        stage ('Deploy'){
            steps {
                echo ' deploying......'

            }
        }
     }
}