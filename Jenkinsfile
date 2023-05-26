node{
    
    stage('Clone repo'){
        git credentialsId: 'GIT-Credentials', url: 'https://github.com/simbu9700/sonarnexusproject.git'
    }
    
     stage('SonarQube analysis') {
    def scannerHome = tool 'sonar-server';
    withSonarQubeEnv('sonar-server') {
      sh "${scannerHome}/bin/sonar-scanner \
      -D sonar.login=admin \
      -D sonar.password=simbu \
      -D sonar.projectKey=studentapp \
      -D sonar.exclusions=vendor/**,resources/**,**/*.java \
      -D sonar.host.url=http://13.113.126.152/:9000/"
    }
  }

}
    
  
