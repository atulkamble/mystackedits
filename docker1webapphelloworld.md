---


---

<h2 id="to-create-a-docker-image-of-a-simple-web-application-on-ec2physical-machine"><strong>// To create a Docker image of a simple web application on EC2/Physical Machine</strong></h2>
<pre><code>mkdir dockerfiles 
New-Item Dockerfile
</code></pre>
<p><strong>OR</strong></p>
<pre><code>touch Dockerfile
</code></pre>
<p><strong>Add following content to file</strong></p>
<pre><code>FROM ubuntu:18.04

#Install dependencies

RUN apt-get update &amp;&amp; \
 apt-get -y install apache2

# Install apache and write hello world message

RUN echo 'Hello World!' &gt; /var/www/html/index.html

# Configure apache

RUN echo '. /etc/apache2/envvars' &gt; /root/run_apache.sh &amp;&amp; \
 echo 'mkdir -p /var/run/apache2' &gt;&gt; /root/run_apache.sh &amp;&amp; \
 echo 'mkdir -p /var/lock/apache2' &gt;&gt; /root/run_apache.sh &amp;&amp; \ 
 echo '/usr/sbin/apache2 -D FOREGROUND' &gt;&gt; /root/run_apache.sh &amp;&amp; \ 
 chmod 755 /root/run_apache.sh

EXPOSE 80

CMD /root/run_apache.sh
</code></pre>
<hr>
<p>docker build -t hello-world .</p>
<p>sudo docker images</p>
<p>docker run -t -i -p 80:80 hello-world</p>
<hr>
<p><a href="http://localhost/">http://localhost/</a>.</p>
<p>docker-machine ip machine-name</p>

