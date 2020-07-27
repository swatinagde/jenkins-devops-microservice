pipeline {
	agent any
	environment{
		dockerHome = tool 'myDocker'
		mavenHome = tool 'myMaven'
		PATH = "$dockerHome/bin:$mavenHome/bin:$PATH"
	}
	stages{
		stage('Checkout'){
			steps{
				sh 'mvn --version'
				sh 'docker version'
			echo("Checkout")
			echo("PATH - $PATH")
			echo("BUILD_NUMBER : $env.BUILD_NUMBER")
			echo("BUILD_ID : $env.BUILD_ID")
			echo("JOB_NAME : $env.JOB_NAME");
			echo("BUILD_TAG : $env.BUILD_TAG");
			}
		}
		stage('Build'){
			steps{
				sh "mvn clean compile"
			echo("Build");
			}
		}
		stage('Test'){
			steps{
				sh "mvn test"
			}
		}
		stage('Integration Test'){
			steps{
			sh "mvn failsafe:integration-test failsafe:verify"
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
