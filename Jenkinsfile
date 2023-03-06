pipeline {
  
  environment {
    apptainerImage = "multiqc"
    apptainerVersion = "1.11"
  }

  agent { label 'apptainer' }
  
  stages {
    stage('Build') {
      steps {
        sh "sudo apptainer build ${apptainerImage}-${apptainerVersion}.sif ${apptainerImage}.${apptainerVersion}"
      }
    }

    stage('Copy') {
      steps {
        sh "cp ${apptainerImage}-${apptainerVersion}.sif /workspace/output"
      }
    }
  }

}