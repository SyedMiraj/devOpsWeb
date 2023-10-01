pipeline {
    agent any
    
    parameters {
         string(name: 'staging_server', defaultValue: 'https://16aa-103-140-176-31.ngrok-free.app', description: 'Remote Staging Server')
    }

stages{
        stage('Build'){
            steps {
                sh 'mvn clean package'
            }
            post {
                success {
                    echo 'Archiving the artifacts'
                    archiveArtifacts artifacts: '**/target/*.war'
                }
            }
        }

        //stage ('Deployments'){
          //  parallel{
            //    stage ("Deploy to Staging"){
              //      steps {
                //        sh "scp -v -o StrictHostKeyChecking=no **/*.war root@${params.staging_server}:/opt/tomcat/webapps/"
                  //  }
               // }
           // }
       // }
    }
}
