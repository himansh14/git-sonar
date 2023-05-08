node{
    stage('Cloning the project from the git'){
        git branch: 'main', credentialsId: 'github', url: 'https://github.com/himansh14/git-sonar.git'
    }
    stage('Sonarqube analysis'){
        def scannerHome = tool 'sonarqube';
        withSonarQubeEnv('sonarqube'){
            sh "${scannerHome}/bin/sonar-scanner \
            -D sonar.login=admin \
            -D sonar.password=@constant14 \
            -D sonar.projectKey=sonarqube-jenkins \
            -D sonar.exclusions=vendor/**,resources/**,**/*.java \
            -D sonar.host.url=http://3.86.100.62:9001/"
        }
    }
}
