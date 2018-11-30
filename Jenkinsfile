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

/*
Rula
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
*/


node {
  checkout scm
  stage('Compilar') {
    echo "Comienza la compilación ..."
      sh 'mvn compile'
  }
  
  stage('Test') {
    echo "Comienzan las pruebas ..."
      sh 'mvn test'
    junit '**/*.xml'
  }
  
  stage('Empaquetar') {
    echo "Comienza el empaquetado ..."
      
    try{
      sh 'mvn package'
    }    
    finally{
        //deleteDir()
    }
  }
}

