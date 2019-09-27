node{
   
   stage("App Build started"){
      echo 'App build started..'
      git credentialsId: 'githubID', url: 'https://github.com/srifeb13/python-docker-app-openshifts.git'
      }
   
   stage('Docker Build') {
     def app = docker.build "srifeb13/itrainpadman"
    }
   
   stage("Tag & Push image"){
      withDockerRegistry([credentialsId: 'dockerID',url: ""]) {
          sh 'docker tag manee2k6/srifeb13 manee2k6/itrainbatman:dev'
          sh 'docker push manee2k6/srifeb13:dev'
          sh 'docker push manee2k6/srifeb13:latest'
      }
    }
    stage("App deployment started"){
     sh 'oc login --token=t01XSPheqChA1n1QxmPCSJAwm5rFNYzb7FvRP9mmg6A --server=https://api.us-east-1.online-starter.openshift.com:6443'
    // sh 'oc new-project creativetech'
      
     sh 'oc new-app shiddu/pythonimage:dev --name python --env NEWRELIC_LICENSE=xxxxxx NEWRELIC_APPNAME=pyapp'
     sh 'oc expose svc python --name=python'
     sh 'oc status'
    }
   
    stage('App deployed to Openshift environment') {
     echo 'App deployed to Openshift environment..'
    }

   


   
























}
