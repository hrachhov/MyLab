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
//                 sh 'mvn clean install package'
                sh 'mvn clean install package'
            }
        }

        // Stage2 : Testing
        stage ('Test'){
            steps {
                echo ' testing......'

            }
        }

        // State 3 : publish the artifacts to Nexux
        stage ('Publish to Nexus'){
            steps{
                nexusArtifactUploader artifacts: [[artifactId: 'VinayDevOpsLab', classifier: '', file: 'target/vinaysdevopslab-0.0.14-SNAPSHOT.war', type: 'war']], credentialsId: '466d7b69-c2c8-4694-9ccf-92ea5b495148', groupId: 'com.vinaysdevopslab', nexusUrl: '54.177.233.199:8081/', nexusVersion: 'nexus3', protocol: 'http', repository: 'VinaysDevOpsLab-SNAPSHOT', version: '0.0.14-SNAPSHOT'
            }
        }
        // Stage 3 : Deploying
        stage('Deploy'){
            steps{
                echo 'deploying....'
            }
        }
        // Stage3 : Publish the source code to Sonarqube
//         stage ('Sonarqube Analysis'){
//             steps {
//                 echo ' Source code published to Sonarqube for SCA......'
//                 withSonarQubeEnv('sonarqube'){ // You can override the credential to be used
//                      sh 'mvn sonar:sonar'
//                 }
//
//             }
//         }

        
        
    }

}