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



or


pipeline {
    agent any
    tools {
        maven 'MAVEN_HOME'
    }
    stages {
        stage('Git Repo & Clean') {
            steps {
                bat "rmdir /s /q SampleMavenJavaProject"
                bat "git clone https://github.com/budarajumadhurika/SampleMavenJavaProject.git"
                bat "mvn clean -f SampleMavenJavaProject/pom.xml"
            }
        }
        stage('Install') {
            steps {
                bat "mvn install -f SampleMavenJavaProject/pom.xml"
            }
        }
        stage('Test') {
            steps {
                bat "mvn test -f SampleMavenJavaProject/pom.xml"
            }
        }
        stage('Package') {
            steps {
                bat "mvn package -f SampleMavenJavaProject/pom.xml"
            }
        }
    }
    post {
        success {
            echo 'Pipeline executed successfully!'
        }
        failure {
            echo 'Pipeline failed. Check the logs for more details.'
        }
    }
}



or



pipeline {
    agent any
    tools {
        maven 'MAVEN_HOME'
    }
    triggers {
        githubPush()
    }
    stages {
        stage('Git Clone') {
            steps {
                bat 'C:\\Windows\\System32\\cmd.exe /c rmdir /s /q ProjectJenkins || echo "No existing directory to delete"'
                bat 'C:\\Windows\\System32\\cmd.exe /c git clone https://github.com/Gayatri2004-09/ProjectJenkins.git'
            }
        }
        stage('Maven Build') {
            steps {
                dir('ProjectJenkins') {
                    bat '"C:\\Program Files\\apache-maven-3.9.9\\bin\\mvn.cmd" clean install'
                }
            }
        }
        stage('Maven Test') {
            steps {
                dir('ProjectJenkins') {
                    bat '"C:\\Program Files\\apache-maven-3.9.9\\bin\\mvn.cmd" test'
                }
            }
        }
        stage('Maven Package') {
            steps {
                dir('ProjectJenkins') {
                    bat '"C:\\Program Files\\apache-maven-3.9.9\\bin\\mvn.cmd" package'
                }
            }
        }
    }
    post {
        success {
            echo ' Build and deployment completed successfully!'
        }
        failure {
            echo ' Build or deployment failed. Check the logs for errors.'
        }
    }
}







<user username="admin" password="12345" roles="manager-gui, admin-gui ,manager-script"/>


    <role rolename="admin-gui,manager-gui,manager-script,manager-jmx,manager-status"/>
<user username="admin" password="12345" roles="manager-gui,admin-gui,manager-script"/>
