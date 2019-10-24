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
    sh "./main"
  }
  stage("archivage") {
    archiveArtifacts artifacts: 'main'
  }
}
