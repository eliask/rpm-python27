rpm-python27
============

An RPM spec file build and alt-install Python 2.7 on RHEL.

To Build:

`sudo yum -y install rpmdevtools && rpmdev-setuptree`

`sudo yum -y install expat-devel db4-devel gdbm-devel sqlite-devel bzip2-devel openssl-devel ncurses-devel readline-devel`

`wget https://raw.github.com/eliask/rpm-python27/master/python27.spec -O ~/rpmbuild/SPECS/python27.spec`

`wget https://raw.github.com/eliask/rpm-python27/master/python27-virtualenv.spec -O ~/rpmbuild/SPECS/python27-virtualenv.spec`

`wget http://www.python.org/ftp/python/2.7.5/Python-2.7.5.tar.bz2 -O ~/rpmbuild/SOURCES/Python-2.7.5.tar.bz2`

`wget https://pypi.python.org/packages/source/v/virtualenv/virtualenv-1.10.1.tar.gz -O ~/rpmbuild/SOURCES/virtualenv-1.10.1.tar.gz`

`QA_RPATHS=$[ 0x0001|0x0010 ] rpmbuild -bb ~/rpmbuild/SPECS/python27.spec`

`QA_RPATHS=$[ 0x0001|0x0010 ] rpmbuild -bb ~/rpmbuild/SPECS/python27-virtualenv.spec`
