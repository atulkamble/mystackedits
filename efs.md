---


---

<p><strong>EFS</strong></p>
<ol>
<li>Navigate to EFS</li>
<li>Create File System</li>
<li>Open Customise</li>
<li>Configure Subnets, Security Groups</li>
<li>Launch 2 instances</li>
<li>Connect through ssh</li>
<li>Check for files which has been created from istances</li>
<li>Terminate efs, instances, check vpc</li>
<li>Terminate security group outbound rules, security groups</li>
</ol>
<p><strong>from 1st instance via ssh</strong></p>
<pre><code>ls /mnt/efs/fs1/
sudo su
echo "hello world" &gt; /mnt/efs/fs1/hello.txt
</code></pre>
<p><strong>from 2nd instance via ssh</strong></p>
<pre><code>ls /mnt/efs/fs1/
</code></pre>

