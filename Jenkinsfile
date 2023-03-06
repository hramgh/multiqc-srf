pipeline {
  
  environment {
    apptainerRecipe = "Apptainer"
    apptainerImage = "multiqc"
    apptainerVersion = "1.14"
  }

  agent { label 'apptainer' }
  
  stages {
    stage('Build') {
      steps {
        sh "sudo apptainer build ${apptainerImage}-${apptainerVersion}.sif ${apptainerRecipe}.${apptainerVersion}"
      }
    }

    stage('Copy') {
      steps {
        sh "cp ${apptainerImage}-${apptainerVersion}.sif /workspace/output"
      }
    }
  }

}