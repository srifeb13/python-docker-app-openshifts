node{
   
   stage("App Build started"){
      echo 'App build started..'
      git credentialsId: 'Github-ID', url: 'https://github.com/itrainavengers/python-docker-app-openshifts.git'
      }
   
   stage('Docker Build') {
     def app = docker.build "manee2k6/itrainavenger"
    }
   
   stage("Tag & Push image"){
      withDockerRegistry([credentialsId: 'dockerID',url: ""]) {
          sh 'docker tag manee2k6/itrainavenger manee2k6/itrainavenger:dev'
          sh 'docker push manee2k6/itrainavenger:dev'
          sh 'docker push manee2k6/itrainavenger:latest'
      }
    }
   
   stage("App deployment started"){
     sh 'oc login --token=U0mNHuUe1VMJNXU7UplhPs46ywPnq6FGfz0cMlQcSuQ --server=https://api.us-east-2.online-starter.openshift.com:6443'
     //sh 'oc new project padmavathy'
     sh 'oc import-image manee2k6/python-app:pattabhi-1.0 --name python-app'
     sh 'oc expose svc python-app --name=python-app'
     sh 'oc status'
    }
   
    stage('App deployed to Openshift environment') {
     echo 'App deployed to Openshift environment..'
    }

   
























}
