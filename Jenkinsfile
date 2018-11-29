/*
pipeline {
  agent any
  stages {
    stage('Etapa 1') {
      steps {
        echo 'Hola mundo'
      }
    }
  }
}
*/

/*
node {
  stage('Build') {
    echo "Helllo"
  }
}
*/

node {
  checkout scm
  stage('Compilar') {
    echo "Comienza la compilación ..."
    withMaven(
       maven:'Maven Defecto (3.6)'
    ){
      sh 'mvn compile'
    }
  }
  
  stage('Test') {
    echo "Comienzan las pruebas ..."
    withMaven(
       maven:'Maven Defecto (3.6)'
    ){
      sh 'mvn test'
    }
  }
  
  stage('Empaquetar') {
    echo "Comienza el empaquetado ..."
    withMaven(
       maven:'Maven Defecto (3.6)'
    ){
      sh 'mvn package'
    }
  }
}

