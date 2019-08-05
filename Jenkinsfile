node{
   
   stage("App Build started"){
      echo 'App build started..'
      git credentialsId: 'Github-ID', url: 'https://github.com/itrainavengers/python-docker-app-openshifts.git'
      }
   
   stage('Docker Build') {
     def app = docker.build "vickeyreddy/itrainavenger"
    }
   
   stage("Tag & Push image"){
      withDockerRegistry([credentialsId:'dockerID',url: ""]) {
          sh 'docker tag vickeyreddy/itrainavenger vickeyreddy/itrainavenger:001'
          sh 'docker push vickeyreddy/itrainavenger:001'
          sh 'docker push vickeyreddy/itrainavenger:latest'
      }
    }
   
   stage("App deployment started"){
     sh 'oc login --token=5DJHETXxbPqVjfDzKM-5Sq1A_bPq_rM_wHYJPf37eH8 --server=https://api.us-east-2.online-starter.openshift.com:6443'
     //sh 'oc new project pythondocker'
     sh 'oc new-app vickeyreddy/python-app:pattabhi-1.0 --name python-app001'
     sh 'oc expose svc python-app001 --name=python-app001'
     sh 'oc status'
    }
   
    stage('App deployed to Openshift environment') {
     echo 'App deployed to Openshift environment..'
    }

   
























}
