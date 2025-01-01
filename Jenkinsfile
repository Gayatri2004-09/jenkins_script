pipeline {
    agent any
    tools {
        maven 'MAVEN_HOME' // Ensure Maven is configured correctly in Jenkins
    }
    triggers {
        githubPush() // This will trigger the pipeline on a GitHub push event
    }
    stages {
        stage('Git Clone and Clean') {
            steps {
                script {
                    try {
                        // Clone the repository
                        bat 'C:\\Windows\\System32\\cmd.exe /c git clone git@github.com:Gayatri2004-09/ProjectJenkins.git'
                        // Ensure we're on the master branch
                        bat 'C:\\Windows\\System32\\cmd.exe /c cd ProjectJenkins && git checkout master'
                    } catch (Exception e) {
                        echo "Git clone or clean failed: ${e}"
                    }
                }
            }
        }
        stage('Maven Clean') {
            steps {
                script {
                    try {
                        bat '"C:\\Program Files\\apache-maven-3.9.9\\bin\\mvn.cmd" clean -f ProjectJenkins'
                    } catch (Exception e) {
                        echo "Maven clean failed: ${e}"
                    }
                }
            }
        }
        stage('Maven Install') {
            steps {
                script {
                    try {
                        bat '"C:\\Program Files\\apache-maven-3.9.9\\bin\\mvn.cmd" install -f ProjectJenkins'
                    } catch (Exception e) {
                        echo "Maven install failed: ${e}"
                    }
                }
            }
        }
        stage('Maven Test') {
            steps {
                script {
                    try {
                        bat '"C:\\Program Files\\apache-maven-3.9.9\\bin\\mvn.cmd" test -f ProjectJenkins'
                    } catch (Exception e) {
                        echo "Maven test failed: ${e}"
                    }
                }
            }
        }
        stage('Maven Package') {
            steps {
                script {
                    try {
                        bat '"C:\\Program Files\\apache-maven-3.9.9\\bin\\mvn.cmd" package -f ProjectJenkins'
                    } catch (Exception e) {
                        echo "Maven package failed: ${e}"
                    }
                }
            }
        }
    }
} 