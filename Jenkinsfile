node{
   
   stage("App Build started"){
      echo 'App build started..'
      git credentialsId: 'Github-ID', url: 'https://github.com/itrainavengers/python-docker-app-openshifts.git'
      }
   
   stage('Docker Build') {
     def app = docker.build "vickeyreddy/itrainavenger"
    }
   
   stage("Tag & Push image"){
      withDockerRegistry([credentialsId: 'dockerID',url: ""]) {
          sh 'docker tag vickeyreddy/itrainavenger vickeyreddy/itrainavenger:001'
          sh 'docker push vickeyreddy/itrainavenger:001'
          sh 'docker push vickeyreddy/itrainavenger:latest'
      }
    }
   
   stage("App deployment started"){
     //sh 'oc login https://api.starter-us-west-1.openshift.com --token=l334xAzzGBl7kvYuUFcvfRCCXMsQxeQJox3pEzbSQrQ'
     //sh 'oc new project padmavathy'
     //sh 'oc new-app manee2k6/python-app:pattabhi-1.0 --name python-app'
     //sh 'oc expose svc python-app --name=python-app'
     //sh 'oc status'
    }
   
    stage('App deployed to Openshift environment') {
     echo 'App deployed to Openshift environment..'
    }

   
























}
