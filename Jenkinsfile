#!/usr/bin/groovy 
pipeline{
	agent any
	stages{
	stage('Prepration and Environment Check'){
			steps{
				build '01_Java_SampleApp_Prepare'
			}
		}
	    stage('Build Application'){
			steps{
				build '02_Java_SampleApp_Build'
			}
		}
		stage('Unit Test'){
			steps{
				build '03_Java_SampleApp_Unit_Test'
			}
		}
		stage('Security Test'){
			steps{
				build '04_Java_SampleApp_Dast'
			}
		}
		stage('Static Code Analysis'){
			steps{
				build '05_Java_SampleApp_StaticCodeAnalysis'
			}
		}
		stage('Smoke Test'){
			steps{
				build '06_Java_SampleApp_SmokeTest'
			}
		}
		stage('Functional Tests'){
			parallel{				
				stage('Regression Test'){
					steps {
						build '07_Java_SampleApp_RegressionTest'
					}
				}				
				stage('API Test'){
					steps{
						build '08_Java_SampleApp_APITest'
					}
				}
			}
		}
	}
}
