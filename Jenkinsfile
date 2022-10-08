pipeline {
       agent {
            label {
                   label 'built-in'
                   customWorkspace '/mnt/docker/3/'
                  }
               }
        stages {
             stage ('git-clone'){
                  steps {
                     sh "rm -rf *"
                     sh "git clone https://github.com/tejasshete244/docker.git -b 22Q3"
                        }
                      }
             stage ('docker-run'){
                  steps {
                     sh "docker stop 22Q3"
                     sh "docker container rm 22Q3"
                     sh "docker run -itdp 8080:80 --name 22Q3 httpd"
                     sh "chmod 777 /mnt/docker/3/docker/index.html"
                     sh "docker cp /mnt/docker/3/docker/index.html 22Q3:/usr/local/apache2/htdocs/"
                     }
                }

           }

    }
