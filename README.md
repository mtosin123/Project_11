project 11 new
adjusted now
new nw




<!-- ############################################
=======================================================================
site.yml freestyle
---
# - hosts: all
# - name: Include dynamic variables 
#   tasks:
#   import_playbook: ../static-assignments/common.yml 
#   include: ../dynamic-assignments/env-vars.yml
#   tags:
#     - always

# -  hosts: webservers
# - name: Webserver assignment
#   import_playbook: ../static-assignments/webservers.yml

 - name: Loadbalancers assignment
       hosts: lb
         - import_playbook: ../static-assignments/loadbalancers.yml
        when: load_balancer_is_required
======================================================================================== -->









<!-- 
######## JENKINS FILE FOR QUICK TASK ########
================================================
project 11 new
adjusted now
new nw

######## JENKINS FILE FOR QUICK TASK ########
================================================
pipeline {
    agent any

  stages {

    stage("Initial cleanup") {
          steps {
            dir("${WORKSPACE}") {
              deleteDir()
            }
          }
        }

    stage('Build') {
      steps {
        script {
          sh 'echo "Building Stage"'
        }
      }
    }

    stage('Test') {
      steps {
        script {
          sh 'echo "Testing Stage"'
        }
      }
    }
    stage('Package') {
      steps {
        script {
          sh 'echo "Packaging"'
        }
      }
    }
    stage('Deploy') {
      steps {
        script {
          sh 'echo "Deploying"'
        }
      }
    }
    stage('Clean up') {
      steps {
        script {
          sh 'echo "Staging"'
        }
      }
    }
    stage('Clean Workspace after build'){
        steps{
          cleanWs(cleanWhenAborted: true, cleanWhenFailure: true, cleanWhenNotBuilt: true, cleanWhenUnstable: true, deleteDirs: true)
        }
    }
    }
} -- -->
