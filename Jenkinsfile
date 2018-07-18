// Global variable section for Wordpress Deployment Pipeline

def registry = '833089950506.dkr.ecr.us-east-1.amazonaws.com'
def app = 'demo-wp'
def tag = env.BUILD_NUMBER

try {
    node {
        
        stage 'Checkout' 
            git 'https://github.com/Anilborra25/wordpress-ecs.git'

        docker.withRegistry("https://${registry}", 'ecr:us-east-1:ecs-wp-demo-cred') {
        
        stage 'Build'
            def appImage = docker.build("${registry}/${app}:${tag}")
              
        stage 'Test'

        stage 'Publish'
            appImage.push()
        }
        
        stage 'Deploy'
    }
} catch (err) {
    currentBuild.result = "FAILED"
    throw err    
} 
