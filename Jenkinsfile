properties([
  pipelineTriggers([pollSCM('H/3 * * * *')]) 
  ])
node() { 
  stage("checkout") {
    cleanWs()
    checkout scm
  }
  stage("build") {
    sh "make" 
  }
  stage("archivage") {
    archiveArtifacts artifacts: 'main'
  }
  stage("exec") {
    sh "./main"
  }
}
