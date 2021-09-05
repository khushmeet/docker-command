# docker-command
## HELPFUL DOCKER COMMANDS
<ol>
<li><a href="https://docs.docker.com/engine/reference/commandline/ps/" rel="nofollow noopener noreferrer" target="_blank">docker ps</a>&#8202; list running containers.&nbsp;</li>
<li><a href="https://docs.docker.com/engine/reference/commandline/ps/" rel="nofollow noopener noreferrer" target="_blank">docker ps -a</a> list all container including stopped container</li>
<li><a href="https://docs.docker.com/engine/reference/commandline/pull/" rel="nofollow noopener noreferrer" target="_blank">docker pull</a>&#8202; download a image from <a href="https://hub.docker.com/" rel="nofollow noopener noreferrer" target="_blank">Docker Hub</a>&nbsp;registry. Link to the docker image is always shown on the right at dockerhub.</li>
<li><a href="https://docs.docker.com/engine/reference/commandline/build/" rel="nofollow noopener noreferrer" target="_blank">docker build</a>&#8202; is used to build your own container based on a Dockerfile. Common use is <em><strong>docker build .</strong></em> to build a container based on the Dockerfile in the current directory (the dot). <em><strong>docker build -t "myimage:latest" .</strong></em> creates a container and stores the image under the given name</li>
<li><a href="https://docs.docker.com/engine/reference/commandline/image/" rel="nofollow noopener noreferrer" target="_blank">docker images</a> or <em><strong>docker image ls</strong></em> shows all local storage images</li>
<li><a href="https://docs.docker.com/engine/reference/run/" rel="nofollow noopener noreferrer" target="_blank">docker run</a>&#8202;&#8202;Run a docker container based on an image, i. e. <em><strong>docker run myimage -it bash</strong></em>. If no local image can be found docker run automatically tries to download the image from Docker hub.</li>
<li><a href="https://docs.docker.com/engine/reference/commandline/logs/" rel="nofollow noopener noreferrer" target="_blank">docker logs</a>&nbsp;display the logs of a container, you specified. To continue showing log updates just use <em><strong>docker logs -f mycontainer</strong></em></li>
<li><a href="https://docs.docker.com/engine/reference/commandline/volume_ls/" rel="nofollow noopener noreferrer" target="_blank">docker volume ls</a>&#8202; lists the&nbsp;<a href="https://docs.docker.com/storage/volumes/" rel="nofollow noopener noreferrer" target="_blank">volumes</a>, which are commonly used for persisting data of Docker containers.</li>
<li><a href="https://docs.docker.com/engine/reference/commandline/network/" rel="nofollow noopener noreferrer" target="_blank">docker network ls</a> - list all networks available for docker container</li>
<li><strong><em>docker network connect <networkname> <container></container></networkname></em></strong> adds the container to the given container network. That enables container communication by simple container name instead of IP.</li>
<li><a href="https://docs.docker.com/engine/reference/commandline/rm/" rel="nofollow noopener noreferrer" target="_blank">docker rm</a>&#8202; &#8202;removes one or more containers.&nbsp;<em><strong>docker rm mycontainer</strong></em>, but make sure the container is not running</li>
<li><a href="https://docs.docker.com/engine/reference/commandline/rmi/" rel="nofollow noopener noreferrer" target="_blank">docker rmi</a> &nbsp;removes one or more images.&nbsp;<em><strong>docker rmi myimage</strong></em>, but make sure no running container is based on that image</li>
<li><a href="https://docs.docker.com/engine/reference/commandline/stop/" rel="nofollow noopener noreferrer" target="_blank">docker stop</a>&#8202; &#8202;stops one or more containers.&nbsp;<strong><em>docker stop mycontainer</em></strong> stops one container, while&nbsp;<strong><em>docker stop $(docker ps -a -q)</em></strong> stops all running containers.&nbsp;</li>
<li><a href="https://docs.docker.com/engine/reference/commandline/start/" rel="nofollow noopener noreferrer" target="_blank">docker start</a> - starts a stopped container using the last state</li>
<li><a href="https://docs.docker.com/engine/reference/commandline/update/" rel="nofollow noopener noreferrer" target="_blank">docker update</a> --restart=no <container> updates container policies, that is especially helpful when your container is stuck in a crash loop</container></li>
<li><a href="https://docs.docker.com/engine/reference/commandline/cp/" rel="nofollow noopener noreferrer" target="_blank">docker cp</a> to copy files from a running container to the host or the way around. <em><strong>docker cp <container>:/etc/file .</container></strong></em> to copy /etc/file to your current directory.</li>
</ol>

## SOME OTHER COMBINATION THAT HELP A LOT

<ul>
<li>kill all running containers with&nbsp;<em><strong>docker kill $(docker ps -q)</strong></em></li>
<li>delete all stopped containers with&nbsp;<em><strong>docker rm $(docker ps -a -q)</strong></em></li>
<li>delete all images with&nbsp;<strong><em>docker rmi $(docker images -q)</em></strong></li>
<li>update and stop a container that is in a crash-loop with <em><strong>docker update --restart=no <id> &amp;&amp; docker stop <id></id></id></strong></em></li>
<li>bash shell into container <em><strong>docker exec -i -t <container> /bin/bash</container></strong></em> - if bash is not available use /bin/sh</li>
<li>bash shell with root if container is running in a different user context <strong><em>docker exec -i -t -u root <container> /bin/bash</container></em></strong></li>
</ul>

## SOME iMPORTANT lINKS
https://gist.github.com/giansalex/2776a4206666d940d014792ab4700d80
