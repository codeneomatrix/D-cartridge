# D-cartridge


D Openshift Cartridge implements vibe.d (http://vibed.org/)

Provide the next URL for cartridge definition when create a new application:
https://raw.githubusercontent.com/codeneomatrix/D-cartridge/master/metadata/manifest.yml

##Example
The most convenient way for use this cartridge it's using Red-Hat Client (Installation, configuration and further info can be found in https://developers.openshift.com/en/managing-client-tools.html), we'll do next things:
* Create your application


#### Create your application
Open your terminal and type:
<pre><code>~ $ rhc app create my_project_name https://raw.githubusercontent.com/codeneomatrix/D-cartridge/master/metadata/manifest.yml</code></pre>


#### Issue
The cartridge is nonfunctional due to the following error:
<pre><code>
Fetching libevent 2.0.1+2.0.16 (getting selected version)...
Failed to execute: 'control start' for /var/lib/openshift/579958117628e138830001a5/d
Using dub registry url 'http://code.dlang.org/'
Refreshing local packages (refresh existing: true)...
Looking for local package map at /var/lib/dub/packages/local-packages.json
Looking for local package map at /var/lib/openshift/579958117628e138830001a5/.dub/packages/local-packages.json
Note: Failed to determine version of package mywebapp at .. Assuming ~master.
Refreshing local packages (refresh existing: false)...
Looking for local package map at /var/lib/dub/packages/local-packages.json
Looking for local package map at /var/lib/openshift/579958117628e138830001a5/.dub/packages/local-packages.json
  Missing dependency vibe-d 0.7.29 of mywebapp
Refreshing local packages (refresh existing: false)...
Looking for local package map at /var/lib/dub/packages/local-packages.json
Looking for local package map at /var/lib/openshift/579958117628e138830001a5/.dub/packages/local-packages.json
  Missing dependency vibe-d 0.7.29 of mywebapp
Checking for missing dependencies.
Using fixed selection vibe-d 0.7.29
Using fixed selection openssl 1.1.4+1.0.1g
Search for versions of botan (1 package suppliers)
Ignoring version specification (>=0.0.0) for path based dependency ../memutils
Return for botan: [1.12.5, 1.12.4, 1.12.3, 1.12.2, 1.12.1, 1.12.0, 1.11.14, 1.11.13, 1.11.12, 1.11.11, 1.11.10, ~master, ~merge-new-algos,
~ldc-compat, ~fix-tls]
Using fixed selection memutils 0.4.6
Search for versions of botan-math (1 package suppliers)
Return for botan-math: [1.0.2, 1.0.1, 1.0.0, ~master]
Sub package botan:base doesn't exist in botan 1.12.0.
Sub package botan:compression doesn't exist in botan 1.12.0.
Sub package botan:tls doesn't exist in botan 1.12.0.
Sub package botan:passhash doesn't exist in botan 1.12.0.
Using fixed selection libevent 2.0.1+2.0.16
Using fixed selection libasync 0.7.9
Acquiring package zip file
/var/lib/openshift/579958117628e138830001a5/.dub: Permission denied
<pre><code>


You must edit <strong>/template/source/app.d</strong> for adding your own content!


##TODO:
* Make tools for easy deploy for parallel processing in openshift
