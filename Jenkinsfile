pipeline {
    agent any

    stages {
      stage('fetch_latest_code') {
        steps {
          git branch: 'main', credentialsId: '76fa3896-9e88-42c9-a8cf-072481da5c0f', url: 'https://github.com/alvaresandres/terraformlab.git'
        }
      }

      stage('TF Init&Plan') {
        steps {
            echo 'Hello-world'
          //sh 'terraform init'
          //sh 'terraform plan'
        }      
      }

      stage('Approval') {
        steps {
          script {
            def userInput = input(id: 'confirm', message: 'Apply Terraform?', parameters: [ [$class: 'BooleanParameterDefinition', defaultValue: false, description: 'Apply terraform', name: 'confirm'] ])
          }
        }
      }

      stage('TF Apply') {
        steps {
            echo 'Hello-world-2'
          //sh 'terraform apply -input=false'
        }
      }
    } 
  }