
node ('master') {
  
   
  stage('SCM') {
    checkout([$class: 'GitSCM', 
        branches: [[name: '*/master']], 
        extensions: [], 
        userRemoteConfigs: [[url: 'https://github.com/Rajee293/helloworldweb.git']]])
    }
  stage('maven-build') {
    sh 'mvn clean package'
  }
  
  input 'Approve for deployment'
  
  stage('deploy') {
      sh 'curl -uuser1.plusforum:AP5LQczWPvpyUyPd9XWdiLu63W1 -L -O  "https://plusforumm.jfrog.io/artifactory/helloworld/Helloworldwebapp-dev.war"'
      sh 'cp ./Helloworldwebapp-dev.war /opt/tomcat.webapps'
      sh '/opt/tomcat/bin/startup.sh'
      
  }
  
  
}
