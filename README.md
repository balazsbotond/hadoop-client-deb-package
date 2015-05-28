Apache Hadoop client Debian package
===========================

A Debian package for installing Hadoop Client 2.2.0. Works on Ubuntu.

**Download the latest pre-built release here:**
https://github.com/balazsbotond/hadoop-client-deb-package/releases

Building the package
--------------------

Clone the repository:

    git clone https://github.com/balazsbotond/hadoop-client-deb-package.git

Build the package using `dpkg-deb`:

    dpkg-deb --build hadoop-client_2.2.0-1

This will create a `hadoop-client-deb-package.deb` file in the current directory.

Installing the package
----------------------

    dpkg -i hadoop-client_2.2.0-1.deb
    apt-get install -f

Testing Hadoop client
---------------------

Use file `/usr/local/hadoop/hadoop-2.2.0/etc/hadoop/core-site.xml` to configure your hadoop.tmp.dir, fs.default.name.
Use file `/usr/local/hadoop/hadoop-2.2.0/etc/hadoop/hadoop-env.sh` to configure hadoop environment variable special JAVA_HOME...
(`export JAVA_HOME=$(readlink -f /usr/bin/java | sed "s:bin/java::")"`)

Use `/usr/local/hadoop/hadoop-2.2.0/bin/hadoop fs -ls /` to check if everything works correctly.