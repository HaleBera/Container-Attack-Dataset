# Container-Attack-Dataset


Nuclei Installation:

  Instead of manuel installation we will install it's docker:
  https://github.com/projectdiscovery/nuclei
  
  

  GO Installation:
  
      Install GO version 1.17.6 from:
  
      https://go.dev/doc/install
      
        
      !The first command may perform arbitrary system changes outside of the security sandbox that snaps        are usually confined to, which may put your system at risk.Thus, use the other two.
    
         $sudo snap install go         # version 1.17.6, or
         $sudo apt  install golang-go
         $sudo apt  install gccgo-go

       Checking the version of GO with the following command:
          
           $ go version
           
       will results with:
       
          go version go1.10.3 gccgo (Ubuntu 8.4.0-1ubuntu1~18.04) 8.4.0 linux/amd64


https://github.com/projectdiscovery/nuclei-templates























hale@hale-Aspire-A315-57G:~$ docker version
Client: Docker Engine - Community
 Version:           20.10.13
 API version:       1.41
 Go version:        go1.16.15
 Git commit:        a224086
 Built:             Thu Mar 10 14:07:52 2022
 OS/Arch:           linux/amd64
 Context:           default
 Experimental:      true
Got permission denied while trying to connect to the Docker daemon socket at unix:///var/run/docker.sock: Get "http://%2Fvar%2Frun%2Fdocker.sock/v1.24/version": dial unix /var/run/docker.sock: connect: permission denied
hale@hale-Aspire-A315-57G:~$ docker pull ^C
hale@hale-Aspire-A315-57G:~$ 
hale@hale-Aspire-A315-57G:~$ sudo docker pull projectdiscovery/nuclei
[sudo] password for hale: 
Using default tag: latest
latest: Pulling from projectdiscovery/nuclei
59bf1c3509f3: Pull complete 
2c881d80c5d6: Pull complete 
0a0c13f80c34: Pull complete 
Digest: sha256:3f853a46d22485fdd36994ac48f91065faa47bba227fc4358ecbadb1df1a8ecd
Status: Downloaded newer image for projectdiscovery/nuclei:latest
docker.io/projectdiscovery/nuclei:latest
hale@hale-Aspire-A315-57G:~$ sudo docker run -ti -d  projectdiscovery/nuclei
3336daf02e658f313b78e5fac5a10ee8a40e13cfa8915e13033f2273dc933cd0
hale@hale-Aspire-A315-57G:~$ sudo su
root@hale-Aspire-A315-57G:/home/hale# 










root@hale-Aspire-A315-57G:/home/hale# docker ps
CONTAINER ID   IMAGE                     COMMAND    CREATED         STATUS         PORTS     NAMES
3336daf02e65   projectdiscovery/nuclei   "nuclei"   8 seconds ago   Up 7 seconds             eager_allen
root@hale-Aspire-A315-57G:/home/hale# docker exec -ti --user root 3336daf02e65 bash
Error response from daemon: Container 3336daf02e658f313b78e5fac5a10ee8a40e13cfa8915e13033f2273dc933cd0 is not running
root@hale-Aspire-A315-57G:/home/hale# 














root@hale-Aspire-A315-57G:/home/hale# ls
 Desktop                      Music         Templates
 dive_0.9.2_linux_amd64.deb   Pictures      Vagrantfile
 dive_0.9.2_linux_amd64.rpm   Public        Videos
 Documents                    RSA_KEY      'VirtualBox VMs'
 Downloads                    RSA_KEY.pub   webmin_docker_and_exp
 examples.desktop             snap
root@hale-Aspire-A315-57G:/home/hale# docker ps
CONTAINER ID   IMAGE     COMMAND   CREATED   STATUS    PORTS     NAMES
root@hale-Aspire-A315-57G:/home/hale# docker ps -a
CONTAINER ID   IMAGE                     COMMAND    CREATED              STATUS                          PORTS     NAMES
3336daf02e65   projectdiscovery/nuclei   "nuclei"   About a minute ago   Exited (0) About a minute ago             eager_allen
root@hale-Aspire-A315-57G:/home/hale# docker logs 3336daf02e65

                     __     _
   ____  __  _______/ /__  (_)
  / __ \/ / / / ___/ / _ \/ /
 / / / / /_/ / /__/ /  __/ /
/_/ /_/\__,_/\___/_/\___/_/   2.6.4

		projectdiscovery.io

[WRN] Use with caution. You are responsible for your actions.
[WRN] Developers assume no liability and are not responsible for any misuse or damage.
[INF] nuclei-templates are not installed, installing...
[INF] Successfully downloaded nuclei-templates (v8.9.3) to /root/nuclei-templates. GoodLuck!
[INF] Using Nuclei Engine 2.6.4 (outdated)
[INF] Using Nuclei Templates 8.9.3 (latest)
[INF] Templates added in last update: 8
[INF] Templates loaded for scan: 3100
root@hale-Aspire-A315-57G:/home/hale# docker run -ti -d projectdiscovery/nuclei 

root@hale-Aspire-A315-57G:/home/hale# docker run -ti -d projectdiscovery/nuclei ^C
root@hale-Aspire-A315-57G:/home/hale# ls
 Desktop                      dive_0.9.2_linux_amd64.rpm   Downloads          Music      Public    RSA_KEY.pub   Templates     Videos            webmin_docker_and_exp
 dive_0.9.2_linux_amd64.deb   Documents                    examples.desktop   Pictures   RSA_KEY   snap          Vagrantfile  'VirtualBox VMs'
root@hale-Aspire-A315-57G:/home/hale# mkdir nuc
root@hale-Aspire-A315-57G:/home/hale# cd nuc
root@hale-Aspire-A315-57G:/home/hale/nuc# docker run -ti -d -v /home/hale/nuc:/tmp projectdiscovery/nuclei -o /tmp




















  
