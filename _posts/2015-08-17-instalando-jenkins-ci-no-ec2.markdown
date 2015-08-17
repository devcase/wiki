---
layout: post
title:  "Instalando Jenkins no EC2"
date:   2015-08-14 13:32:38
categories: web
excerpt: "Instalando Jenkins no EC2"
author: Thiago Hirata
---

# Sumário

   1. Criar VPC, se não tiver uma disponível
   2. Criar instância EC2
    * AMI: [Amazon Linux AMI] (https://aws.amazon.com/pt/amazon-linux-ami/2015.03-release-notes/)
    * [Como acessar via SSH](http://docs.aws.amazon.com/AWSEC2/latest/UserGuide/AccessingInstancesLinux.html#AccessingInstancesLinuxSSHClient)
   3. Download do [Jenkins CI](https://jenkins-ci.org/)
   4. Executar jenkins como daemon e superuser: `nohup java -jar ~/bin/jenkins.war  --httpPort=80 > ~/logs/jenkins.log &`
