node{
   
   stage("App Build started"){
      echo 'App build started..'
      git credentialsId: 'githubID', url: 'https://github.com/srifeb13/python-docker-app-openshifts.git'
      }
   
   stage('Docker Build') {
     def app = docker.build "srifeb13/itrain-padman-py-app"
    }
   
   stage("Tag & Push image"){
      withDockerRegistry([credentialsId: 'dockerID',url: 'https://cloud.docker.com/u/itrainsri/repository/registry-1.docker.io/itrainsri/docker-images']) {
          sh 'docker tag srifeb13/itrain-padman-py-app srifeb13/itrain-padman-py-app:dev'
          sh 'docker push srifeb13/itrain-padman-py-app:dev'
          sh 'docker push srifeb13/itrain-padman-py-app:latest'
      }
    }
    stage("App deployment started"){
     //sh 'oc login --token=t01XSPheqChA1n1QxmPCSJAwm5rFNYzb7FvRP9mmg6A --server=https://api.us-east-1.online-starter.openshift.com:6443'
          // sh 'oc new-project creativetech'
      
    // sh 'oc new-app shiddu/pythonimage:dev --name python --env NEWRELIC_LICENSE=xxxxxx NEWRELIC_APPNAME=pyapp'
    // sh 'oc expose svc python --name=python'
    // sh 'oc status'
    }
   
    stage('App deployed to Openshift environment') {
     echo 'App deployed to Openshift environment..'
    }

   


   
























}
