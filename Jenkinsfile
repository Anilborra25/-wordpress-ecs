// Global variable section for Wordpress Deployment Pipeline

def jenkins = 'low-risk-vpc'
def registry = '833089950506.dkr.ecr.us-east-1.amazonaws.com'
def project = 'demo-wp'

try {
    node {
        stage 'Code Checkout'
        // checkout scm 

        stage 'Build'

        stage 'Test'

	stage 'Package'

        stage 'Publish'

        stage 'Deploy'

    }
} catch (err) {
    currentBuild.result = "FAILED"
    throw err    
} 
