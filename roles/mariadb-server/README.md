# MariaDB Server instalation role

This simple role aims to perform a secure installation of MariaDB 10.1 server
on Ubuntu 14.04 LTS and Debian 8 Jessie. Furthermore it accomplishes the same
actions of *mysql_secure_installation*.

**Only for Ubuntu 14.04 LTS**:

The official Ubuntu 14.04 LTS repository comes with MariaDB 5.5, so the role
adds the repository for the 10.1 version.
