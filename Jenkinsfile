node {
  
        stage('Checkout') {
        // Cloning Repo
           url: 'https://github.com/pushOrganization/EMS-Application.git'
        }    
        
        stage('build') {
        // Building Code
           sh 'mvn clean install'
        }
        
        stage('Archive Artefact') {
            // Archive Artefact after build
            archive 'excludes: '', includes: 'target/*.war''    
        }
}
