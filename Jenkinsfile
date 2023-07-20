pipeline {
  agent any
  stages {
    stage ('23Q1') {
      steps {
        sh "yum install docker -y"
        sh "systemctl start docker"
        sh "systemctl enable docker"
        
        sh "docker system prune -a -f"
        sh "docker run -itdp 80:80 --name brijal httpd"
        sh "docker cp BRIJAL brijal:/usr/local/apache2/htdocs"
        sh "docker exec brijal chmod -R 777 /usr/local/apache2/"
      }
    }
  }
}
