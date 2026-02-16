pipeline{
  agent any
  tools {
      maven "Maven Apache"
  }
  stages{
    stage('Checkout'){
      steps{
        //Clonar repositorio git
        git url: 'https://github.com/alonlain/prueba.git'
      }
    }
    stage('Build'){
      steps{
        //Compilar
        script{
          //instalar
          if (!isUnix()){
              bat 'mvn -version || echo Maven is not installed'
          }else{
              sh 'mvn -version || echo Maven is not installed'
          }

           //Compilar el proyecto
            sh 'mvn clean install'
        }
      }
    post{
      success{
        echo 'Compilación correcta'
      }
      failure{
        echo 'Cascó'
      }
    }
    }
  }
}
