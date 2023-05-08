node{
    stage('Cloning the project from the git'){
        git branch: 'main', credentialsId: 'github', url: 'https://github.com/himansh14/git-sonar.git'
    }
    stage('Sonarqube analysis'){
        def scannerHome = tool 'sonarqube';
        withSonarQubeEnv(){
            sh "${scannerHome}/bin/sonar-scanner \
            -D sonar.projectKey=sonarqube-jenkins"
        }
    }
}
