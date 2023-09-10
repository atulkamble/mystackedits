---


---

<p>Docker Webbsite<br>
<a href="https://www.docker.com/">https://www.docker.com/</a></p>
<p>Docker Community:<br>
<a href="https://www.docker.com/community/">https://www.docker.com/community/</a></p>
<p><strong>Update EC2 -Ubuntu instance</strong></p>
<pre><code>sudo apt update
</code></pre>
<p><strong>Install Docker</strong></p>
<pre><code>sudo apt install docker
OR
sudo snap install docker
OR
sudo apt install docker.io
</code></pre>
<p><strong>Check docker info</strong></p>
<pre><code>docker info
sudo docker info
</code></pre>
<p><strong>Sign in to Docker Hub Website</strong><br>
<a href="https://hub.docker.com/">https://hub.docker.com/</a><br>
note down username &amp; password</p>
<p>Enter following command in EC2</p>
<pre><code>sudo docker login
</code></pre>
<p>Enter username &amp; Password</p>
<p><strong>Pull Docker Image | Hello World</strong></p>
<pre><code>sudo docker pull hello-world:latest
</code></pre>
<p><strong>Pull &amp; run Docker Image -Wordpress</strong></p>
<pre><code>sudo docker run -p 80:80 wordpress:latest
</code></pre>
<p>Check public ip of EC2 in browser with http</p>
<p><strong>Remove running containers</strong></p>
<pre><code>sudo docker images
sudo docker ps -a
sudo docker stop (container id)
sudo docker rm (container id)
</code></pre>
<p><strong>Open Amazon Public Gallary</strong><br>
<em>Search for nginx</em><br>
or navigate to URL**<br>
<a href="https://gallery.ecr.aws/nginx/nginx">https://gallery.ecr.aws/nginx/nginx</a></p>
<p><strong>Run nginx server docker image in EC2 | Allocate port 80</strong></p>
<pre><code>sudo docker run -p 80:80 public.ecr.aws/nginx/nginx:stable-perl
</code></pre>
<p><em>Copy public ip of EC2 Instance &amp; paste in browser</em></p>

