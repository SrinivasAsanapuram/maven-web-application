node{
    def mavenHome = tool name: 'maven3.9.6'
    stage('CheckoutCode'){
        git 'https://github.com/SrinivasAsanapuram/maven-web-application.git'
    }
    stage('Build'){
        sh "${mavenHome}/bin/mvn clean package"
    }
    stage('ExecuteSonarqubeReport'){
        sh "${mavenHome}/bin/mvn clean sonar:sonar"
    }
     stage('UploadArtifactsIntoNeus'){
        sh "${mavenHome}/bin/mvn clean deploy"
    }
