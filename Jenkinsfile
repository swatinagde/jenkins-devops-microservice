pipeline {
	agent any
	environment{
		dockerHome = tool 'myDocker'
		mavenHome = tool 'myMaven'
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
	}
	stages{
		stage('Build'){
			steps{
				sh 'mvn --version'
				sh 'docker version'
			echo("Build")
			echo("PATH - $PATH")
			echo("BUILD_NUMBER : $env.BUILD_NUMBER")
			echo("BUILD_ID : $env.BUILD_ID")
			echo("JOB_NAME : $env.JOB_NAME");
			echo("BUILD_TAG : $env.BUILD_TAG");
			}
		}
		stage('Test'){
			steps{
			echo("Test");
			}
		}
		stage('Integration Test'){
			steps{
			echo("Integration Test");
			}
		}
	}
	post{
		always{
			echo("Running always");
		}
		success{
			echo("Success success");
		}
		failure{
			echo("Fail fail");
		}
	}
}
