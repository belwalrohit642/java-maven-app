#!/usr/bin/env groovy

@Library('jenkins-shared-library') _

pipeline {
    agent any
    stages {
        stage("init") {
            steps {
                script {
                    gv = load "script.groovy"
                }
            }
        }
  stage('Code Checkout') {
            steps {
                script {
                  def workingDir = checkoutCode("https://github.com/belwalrohit642/java-maven-app.git", "master")
                  echo $workingDir
                }
            }
        }
        
        stage("build jar") {
            steps {
                script {
                    echo "building jar"
                    buildJar()
                }
            }
        }
        stage("build image") {
            steps {
                script {
                    echo "building image"
               //     buildImage() 'belwalrohit642/java-app:2.0'
                }
            }
        }
        stage("deploy") {
            steps {
                script {
                    echo "deploying"
                    //gv.deployApp()
                }
            }
        }
    }   
}
