node {
  stage('🚧 Checkout') {
    println("☘️" + env.BRANCH_NAME)
    checkout scm  
  }
  stage('📦 Build') {
    println("building ...")
    def nodeHome = tool name: 'nodejs', type: 'jenkins.plugins.nodejs.tools.NodeJSInstallation'
    env.PATH = "${nodeHome}/bin:${env.PATH}"
    sh "npm install"
    sh "npm test"  
  }
  stage('🚢 Check if Deploy') {
    println("☘️" + env.BRANCH_NAME)
    if(env.BRANCH_NAME.equals("master")) {
      stage('Deploy 🚀') {
        println("🎉 it's time to deploy")
      }
    }
  }
