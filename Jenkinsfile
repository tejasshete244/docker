pipeline {
       agent {
            label {
                   label 'built-in'
                   customWorkspace '/mnt/docker/1/'
                  }
               }
        stages {
             stage ('git-clone'){
                  steps {
                     sh "rm -rf *"
                     sh "git clone https://github.com/tejasshete244/docker.git -b 22Q1"
                        }
                      }
             stage ('docker-run'){
                  steps {
                     sh "docker stop 22Q1"
                     sh "docker container rm 22Q1"
                     sh "docker run -itdp 80:80 --name 22Q1 httpd"
                     sh "docker cp /mnt/docker/1/docker/index.html 22Q1:/usr/local/apache2/htdocs/"
                     sh "docker exec 22Q1 bash"
                     sh "chmod -R 777 /usr/local/apache2/htdocs bash"
                     
                     }
                }

           }

    }
