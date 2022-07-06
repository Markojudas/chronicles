---
title: MongoDB and Fedora
date: 2022-07-05 21:32
---

<!-- markdownlint-disable -->

Today I started the mongodb module for my Go Web Dev. Yes, I am still working through this course. Time is limited between this course, leetcoding, job-hunting, and actual work and regular living. Installing mongodb on fedora 36 proved to be a pain in ass, to say the least. I had to do the following:

<p><h2>Install MongoDB</h2><p>
<p><ol>
    <li>Create a <code>/etc/yum.repos.d/mongodb-org-5.0.repo</code> file to install directly using yum/dnf<br>
    <pre><code>[mongodb-org-5.0]
name=MongoDB Repository
baseurl=https://repo.mongodb.org/yum/amazon/2/mongodb-org/5.0/x86_64/
gpgcheck=1
enabled=1
gpgkey=https://www.mongodb.org/static/pgp/server-5.0.asc</code></pre></li>
    <br>
    <li>Use <code>copr</code> to satisfy the libcrypto and libssl dependencies:<br>
    <code>dnf copr enable dioni21/compat-openssl10</code></li>
    <br>
    <li><code>sudo dnf install -y mongodb-org</code></li>
</ol></p>
<br>

<p><h2>Permissions</h2></p>
<pre><code>sudo chown -R mongod:mongod /var/lib/mongo/
sudo chown mongod:mongod /tmp/mongod-27017.sock</code></pre>
<br>

<p><h2>Modify the mongo.conf file</h2></p>
<code>sudo vim /etc/mongod.conf</code></p>
Add the following:
<pre><code>Security:
    authorization: enabled</code></pre>

<p><h2>Start, check, and enable the service</h2></p>
<code>sudo systemctl start mongod<br></code>
<code>sudo systemctl status mongod<br></code>
<code>sudo systemctl enable mongod<br></code>
<br>

This should do the trick!

If a warning comes up regarding `access control` then we have to stop mongod, and start it again without access control. Then create an user. See docs: <a href="https://www.mongodb.com/docs/manual/tutorial/configure-scram-client-authentication/" target="_blank" rel="noopener noreferrer">USE SCRAM to Authenticate Clients</a>

This whole ordeal took me almost the whole day! uff. The item I'll concentrate on tomorrow will be creating proper documentations for my WFA (windows Form Applications) projects.

Until next time,

Jose aka Markojudas
