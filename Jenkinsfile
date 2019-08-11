node{
   
   stage("App Build started"){
      echo 'App build started..'
      git credentialsId: 'Github-ID', url: 'https://github.com/itrainspartans/python-docker-app-openshifts.git'
      }
   
   stage('Docker Build') {
     def app = docker.build "manee2k6/itrainspartans"
    }
   
   stage("Tag & Push image"){
      withDockerRegistry([credentialsId: 'dockerID',url: ""]) {
          sh 'docker tag manee2k6/itrainspartans manee2k6/itrainspartans:dev'
          sh 'docker push manee2k6/itrainspartans:dev'
          sh 'docker push manee2k6/itrainspartans:latest'
      }
    }
   
   stage("App deployment started"){
     
    }
   
    stage('App deployed to Openshift environment') {
     echo 'App deployed to Openshift environment..'
    }

   
























}
