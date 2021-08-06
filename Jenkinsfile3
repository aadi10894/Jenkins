#!/usr/bin/env groovy

@Library('Shared_Library@main') 

pipeline{
      	agent {label 'Agent_2_Windows'}
	{
                docker {
                image 'maven:3-openjdk-11'
                args '-v $HOME/.m2:/root/.m2'
                }
            }
        
        stages{

              stage('maven build'){
                  steps{
                      script{
		    	                sh "mvn clean install"
                      	  }
               	     }  
                 }	
                 
                 stage ('Check logs') {
                    steps {
                        filterLogs ('WARNING', 5)
                    }
                }
		
           }	       	     	         
}
