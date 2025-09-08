pipeline {
    agent any
 tools {
        maven "Maven3.9"
        jdk "jdk17"
    }
    stages {
        stage('Git checkout') {
            steps {
                git branch: 'jenkins-ci', url: 'https://github.com/myfirstgitravindra/vprofile-project-jenkins-ci.git'
            }
        }
        
        stage('Build') {
            steps {
                sh 'mvn -s settings.xml -DskipTests install'
            }
            post {
                success {
                    echo "Now Archiving."
                    archiveArtifacts artifacts: '**/*.war'
                }
            }
        }

    }