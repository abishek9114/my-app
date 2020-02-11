node{
  stage('SCM Checkout'){  
  git 'https://github.com/abishek9114/my-app.git'
  }
  
  stage('Compile-Package'){
    def mvnHome = tool name: 'maven-plugin', type: 'maven'
    sh "${mvnHome}/bin/mvn package"
  }



}
