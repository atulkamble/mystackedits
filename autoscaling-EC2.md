---


---

<p><strong>Autoscaling Group</strong></p>
<ol>
<li>Create Autoscaling group from EC2 Tab</li>
<li>Separate Security Group</li>
<li>Select Subnets</li>
<li>Create Template | Within Template try following Code</li>
<li>Select Custom Data Setting at last | OS - Amazon Linux 2023 | Paste following code.</li>
<li>Monitor Changes</li>
<li>Edit minimum, desired, maximum instances configuration from Autoscaling Group Setting</li>
</ol>
<p><strong>Steps for terminating</strong></p>
<ul>
<li>
<p>Delete Autoscaling Group</p>
</li>
<li>
<p>Delete Security Group</p>
</li>
<li>
<p>Delete Launch Templates | EC2 Tab</p>
</li>
<li>
<p>Delete Subnet</p>
<p>#!/bin/bash<br>
yum update -y<br>
yum install httpd -y<br>
yum install php -y<br>
service httpd start<br>
service httpd enable<br>
chown -R ec2-user:apache /var/www<br>
chmod 2775 /var/www<br>
cd<br>
echo “&lt;?php phpinfo(); ?&gt;” &gt; /var/www/html/phpinfo.php</p>
</li>
</ul>
<p><strong>OR</strong></p>
<pre><code>!/bin/bash 
yum update -y 
yum install -y httpd 
systemctl start httpd 
systemctl enable httpd 
chmod 777 /var/www/html/ 
echo "&amp;lt;h1&amp;gt; hello from atul $(hostname -f) &lt;/h1&gt;"&gt;/var/www/html/index.html
</code></pre>

