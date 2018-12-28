node {
   
   stage('compile_and_package') {
       checkout scm
   bat 'mvn clean package -DskipTests'
}
   stage('unit_test') {
    
    bat 'mvn surefire:test'
    step([$class: 'Publisher'])
  
}

   stage('code_analysis') {
    
    withSonarQubeEnv {
        bat 'mvn sonar:sonar'
}
  
}

}
