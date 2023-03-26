#! /usr/bin/env groovy

pipeline {

  agent any
  environment {
    SPECTRAL_DSN = 'https://spu-f641f73b9c03467eb3544c4095b3d04e@get.spectralops.io'
  }
  stages {
    stage('install Spectral') {
      steps {
        sh "curl -L 'https://spectral-eu.checkpoint.com/latest/x/sh?dsn=$SPECTRAL_DSN' | sh"
      }
    }
    stage('scan for issues') {
      steps {
        sh " $HOME/.spectral/spectral scan --engine-kinds oss"
      }
    }
  }
}
