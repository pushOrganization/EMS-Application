node {
  
        stage('Checkout') {
        // Cloning Repo
           url: 'https://github.com/pushOrganization/EMS-Application.git'
        }    
        
        stage('build') {
        // Building Code
           sh 'mvn clean install'
        }
        
        stage('Archive Artifact') {
            // Archive Artifact after build
           archiveArtifacts 'target/*.war'  
        }
}
