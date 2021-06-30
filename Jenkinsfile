pipeline {
    agent any

    stages {
      stage('fetch_latest_code') {
        steps {
          git credentialsId: '', url: 'https://github.com/alvaresandres/terraformlab.git'
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