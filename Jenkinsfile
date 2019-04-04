#!groovy
@Library('SoloPipeline')
import com.soloplan.*

pipeline {
  agent {
    label 'dotnet-framework'
  }

  stages {
    stage('Agent info') {
      steps {
        stepAgentInfo()
      }
    }

    stage('Build') {
      steps {
        stepMSBuild(project: 'src/log4net.sln')
      }
    }

    stage('Publish') {
      steps {
        stepPublishArtifacts(bucket: "log4net-netstandard2.0", filder: "bin/release/netstandard2.0")
      }
    }
  }
}
