pipeline {
       agent {
            label {
                   label 'built-in'
                   customWorkspace '/mnt/docker/2/'
                  }
               }
        stages {
             stage ('git-clone'){
                  steps {
                     sh "rm -rf *"
                     sh "git clone https://github.com/tejasshete244/docker.git -b 22Q2"
                        }
                      }
             stage ('docker-run'){
                  steps {
                     sh "docker run -itdp 90:80 --name 22Q2 httpd"
                     sh "chmod 777 /mnt/docker/2/docker/index.html"
                     sh "docker cp /mnt/docker/2/docker/index.html 22Q2:/usr/local/apache2/htdocs/"
                     }
                }

           }

    }
