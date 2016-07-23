# D-cartridge


D Openshift Cartridge



Provide the next URL for cartridge definition when create a new application:
https://raw.githubusercontent.com/codeneomatrix/D-cartridge/master/metadata/manifest.yml

##Example
The most convenient way for use this cartridge it's using Red-Hat Client (Installation, configuration and further info can be found in https://developers.openshift.com/en/managing-client-tools.html), we'll do next things:
* Create your application
* Login and using D
* Optionally start the web server and test

#### Create your application
Open your terminal and type:
<pre><code>~ $ rhc app create my_project_name https://raw.githubusercontent.com/codeneomatrix/D-cartridge/master/metadata/manifest.yml
Your application 'my_project_name' is now available.
  URL:        http://my_project_name-your_user.rhcloud.com/
  SSH to:     55a5cdf...@my_project_name-your_user.rhcloud.com
  Git remote: ssh://55a5cdf...@my_project_name-your_user.rhcloud.com/~/git/my_project_name
.git/
  Cloned to:  ~/my_project_name
</code></pre>
Here "my_project_name" is the project's name that you choose, "your_user" is the username registered at openshift


#### Login and using D
<pre><code>~ $ rhc ssh my_project_name
</code></pre>

#### Start web server
If not already started, you can start web server with:

Using Red-Hat client:
<pre><code>~ $ rhc app start -a my_project_name</code></pre>

Or from ssh connection, inside openshift terminal:
<pre><code>[my_project_name-your_user.rhcloud.com 55a5cdf...]\> gear start</code></pre>

Now you can test the next urls in your browser:
<pre><code>http://my_project_name-your_user.rhcloud.com
http://my_project_name-your_user.rhcloud.com/welcome.html
http://my_project_name-your_user.rhcloud.com/static/test.html
</code></pre>

By default, all files that have no extension will be displayed .d:
<pre><code>http://my_project_name-your_user.rhcloud.com/server.d   # 404: Not Found</code></pre>



You must edit <strong>server.d</strong> for adding your own content! You can see the original code at https://github.com/codeneomatrix/D-cartridge/blob/master/template/server.d


##TODO:
* Make tools for easy deploy for parallel processing in openshift
