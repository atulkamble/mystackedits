---


---

<p>Add following <strong>Custom data</strong> tab of <strong>EC2 Configuration | Advanced</strong></p>
<p><strong>Launching EC2 Webserver | httpd</strong></p>
<pre><code>!/bin/bash 
yum update -y 
yum install -y httpd 
systemctl start httpd 
systemctl enable httpd 
chmod 777 /var/www/html/ 
echo "&lt;h1&gt; hello from $(hostname -f)
&lt;/h1&gt;"&gt;/var/www/html/index.html
</code></pre>
<p><strong>Launching Php Webserver on EC2</strong></p>
<pre><code>#!/bin/bash
yum update -y
yum install httpd -y
yum install php -y
service httpd start
service httpd enable
chown -R ec2-user:apache /var/www
chmod 2775 /var/www
cd
echo "&lt;?php phpinfo(); ?&gt;" &gt; /var/www/html/phpinfo.php
</code></pre>

