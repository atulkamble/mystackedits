---


---

<p>// Installing Docker on Amazon Linux 2</p>
<p>sudo yum update -y</p>
<p>sudo yum install docker -y</p>
<p>sudo service docker start</p>
<p>sudo systemctl enable docker</p>
<p>sudo usermod -a -G docker ec2-user</p>
<p>docker info</p>

