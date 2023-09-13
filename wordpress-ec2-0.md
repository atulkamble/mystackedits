---


---

<h2 id="task-host-a-wordpress-blog-on-amazon-linux-2023"><strong>Task: Host a WordPress blog on Amazon Linux 2023</strong></h2>
<p><strong>Update instance</strong></p>
<pre><code>sudo yum update -y
</code></pre>
<p><strong>download pacakges</strong></p>
<pre><code>sudo dnf install wget php-mysqlnd httpd php-fpm php-mysqli mariadb105-server php-json php php-devel -y
</code></pre>
<p><strong>download wordpress</strong></p>
<pre><code>wget https://wordpress.org/latest.tar.gz
</code></pre>
<p><strong>Unzip and unarchive the installation package. The installation folder is unzipped to a folder called wordpress.</strong></p>
<pre><code>tar -xzf latest.tar.gz
</code></pre>
<p><strong>database configurations</strong></p>
<pre><code>sudo systemctl start mariadb httpd
</code></pre>
<p><strong>signing to database</strong></p>
<pre><code>sudo mysql -u root -p

CREATE USER 'wordpress-user'@'localhost' IDENTIFIED BY 'Atul@123';

CREATE DATABASE `wordpress-db`;

GRANT ALL PRIVILEGES ON `wordpress-db`.* TO "wordpress-user"@"localhost";

FLUSH PRIVILEGES;
</code></pre>
<p><strong>get out of database</strong></p>
<pre><code>exit
</code></pre>
<p><strong>To create and edit the wp-config.php file</strong></p>
<pre><code>cp wordpress/wp-config-sample.php wordpress/wp-config.php
</code></pre>
<p><strong>edit configuration file</strong></p>
<pre><code>nano wordpress/wp-config.php
</code></pre>
<p><strong>Add following details as per the database details<br>
in a wp-config file</strong></p>
<pre><code>define('DB_NAME', 'wordpress-db');

define('DB_USER', 'wordpress-user');

define('DB_PASSWORD', 'your_strong_password');
</code></pre>
<p><strong>Create Authentication Unique Keys</strong></p>
<p><a href="https://api.wordpress.org/secret-key/1.1/salt/">https://api.wordpress.org/secret-key/1.1/salt/</a></p>
<p><strong>Under Apache Document Root</strong></p>
<pre><code>sudo cp -r wordpress/* /var/www/html/
</code></pre>
<p><strong>Alternative Directory</strong></p>
<pre><code>sudo mkdir /var/www/html/blog
sudo cp -r wordpress/* /var/www/html/blog/
</code></pre>
<p><strong>To allow WordPress to use permalinks</strong></p>
<p><strong>edit config file</strong></p>
<pre><code>sudo nano /etc/httpd/conf/httpd.conf
</code></pre>
<p><strong>Search following under lines</strong></p>
<p>*&lt;Directory “/var/www/html”&gt;</p>
<p><em>Find the section that starts with &lt;Directory “/var/www/html”&gt;</em>*</p>
<p>Change the <strong>AllowOverride None</strong> line in the above section to read <strong>AllowOverride All</strong>.</p>
<p><strong>Install the PHP graphics drawing library on Amazon Linux 2023</strong></p>
<pre><code>sudo dnf install php-gd -y
sudo dnf list installed | grep php-gd
</code></pre>
<p><strong>Add Permissions on webserver</strong></p>
<pre><code>sudo chown -R apache /var/www

sudo chgrp -R apache /var/www

sudo chmod 2775 /var/www

sudo systemctl restart httpd
</code></pre>
<p><strong>Php Page</strong></p>
<pre><code>http://your-ec2-ip/wp-admin/install.php
</code></pre>
<p><strong>Wordpress Login Page</strong></p>
<pre><code>http://your-ec2-ip/wp-login.php
</code></pre>

