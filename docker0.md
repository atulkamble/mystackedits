---


---

<p><strong>checking version</strong></p>
<pre><code>- docker info
</code></pre>
<p><strong>Task 1: Download and install docker desktop on your machine.</strong><br>
for windows install WSL from powershell<br>
Command: <code>wsl --install</code><br>
Reference:<br>
<a href="https://learn.microsoft.com/en-us/windows/wsl/install">https://learn.microsoft.com/en-us/windows/wsl/install</a><br>
<a href="https://learn.microsoft.com/en-us/windows/wsl/install">https://www.docker.com/products/docker-desktop/</a></p>
<p>For mac<br>
Refer: <a href="https://docs.docker.com/desktop/install/mac-install/">https://docs.docker.com/desktop/install/mac-install/</a></p>
<p>Task 2: Create docker hub account<br>
Refer website <a href="https://hub.docker.com/">https://hub.docker.com/</a></p>
<p>Task 3: check version of docker from shell/powershell</p>
<p>Task 4: Launch EC2 Instance - Linux Type OR try on physical linux OS OR try on WSL-<br>
Install docker on it.</p>
<p>Refer command : (debian type of linux)</p>
<pre><code>sudo apt update -y

sudo apt install docker
</code></pre>
<p>or</p>
<pre><code>sudo snap install docker 
</code></pre>
<p>or</p>
<pre><code>sudo apt install docker.io
</code></pre>
<p>Task 5: pull hello-world image to local docker system.<br>
Commands:</p>
<pre><code>sudo docker pull hello-world:latest

sudo docker run hello-world:latest
</code></pre>
<p>Task 6: pull hello-world-python image &amp; run it<br>
Command:</p>
<pre><code>docker run -p 5000:5000 in28min/hello-world-python:0.0.1.RELEASE
</code></pre>
<p>Note: check <a href="http://localhost:5000">http://localhost:5000</a> in browser</p>

