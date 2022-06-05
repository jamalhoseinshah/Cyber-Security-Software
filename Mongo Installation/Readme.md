

Install MongoDB Enterprise Edition

Follow these steps to install MongoDB Enterprise Edition using the yum package manager.


Configure repository.
Create an /etc/yum.repos.d/mongodb-enterprise-5.0.repo file so that you can install MongoDB enterprise directly using yum:

[mongodb-enterprise-5.0]
name=MongoDB Enterprise Repository
baseurl=https://repo.mongodb.com/yum/redhat/$releasever/mongodb-enterprise/5.0/$basearch/
gpgcheck=1
enabled=1
gpgkey=https://www.mongodb.org/static/pgp/server-5.0.asc

NOTE
If you have a mongodb-enterprise.repo file in this directory from a previous installation of MongoDB, you should remove it. Use the mongodb-enterprise-5.0.repo file above to install MongoDB 5.0.

You can also download the .rpm files directly from the MongoDB repository. Downloads are organized by Red Hat / CentOS version (e.g. 7), then MongoDB release version (e.g. 5.0), then architecture (e.g. x86_64).

Prior to MongoDB 5.0, odd-numbered MongoDB release versions, such as 4.3, were development releases. Beginning with MongoDB 5.1, MongoDB has quarterly rapid releases. For more information on the differences between rapid and long-term support releases, see MongoDB Versioning.


Install the MongoDB Enterprise packages.
Install MongoDB Enterprise 5.0.
Issue the following command:

sudo yum install -y mongodb-enterprise

Install a specific release of MongoDB Enterprise.
To install a specific release, you must specify each component package individually along with the version number, as in the following example:

sudo yum install -y mongodb-enterprise-5.0.6 mongodb-enterprise-database-5.0.6 mongodb-enterprise-server-5.0.6 mongodb-enterprise-shell-5.0.6 mongodb-enterprise-mongos-5.0.6 mongodb-enterprise-tools-5.0.6

If you only install mongodb-enterprise=5.0.6 and do not include the component packages, the latest version of each MongoDB package will be installed regardless of what version you specified.

Pin a specific version of MongoDB Enterprise.
Although you can specify any available version of MongoDB Enterprise, yum upgrades the packages when a newer version becomes available. To prevent unintended upgrades, pin the package by adding the following exclude directive to your /etc/yum.conf file:

exclude=mongodb-enterprise,mongodb-enterprise-database,mongodb-enterprise-server,mongodb-enterprise-shell,mongodb-enterprise-mongos,mongodb-enterprise-tools


 
