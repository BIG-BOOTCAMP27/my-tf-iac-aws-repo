pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
            checkout([$class: 'GitSCM', branches: [[name: '*/dev']], extensions: [], userRemoteConfigs: [[url: 'https://github.com/BIG-BOOTCAMP27/my-tf-iac-aws-repo']]])          
          }
        }
        
        stage ("terraform init") {
            steps {
                sh ('terraform init') 
            }
        }
        
        stage ("terraform Action") {
            steps {
                echo "Terraform action is --> ${action}"
                sh ('terraform ${action} --auto-approve') 
           }
        }
    }
}
