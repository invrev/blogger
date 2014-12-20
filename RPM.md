#
* Erase the package from the system and removes the files
`rpm -e  <rpm_package> `

* Safe erase first test and then erase
`rpm -e --test <rpm_package>`


##### RPM 
Package = application
Management includes following interfaces
1.install
2.uninstall
3.upgrade 
4.query
Used a lot
5.dependency mgmt
used database : Berkley DB

% : scriplet
use of test_db to install the RPMs temproarily.

rpm : local repo
yum : remote repo
yumdb
rpmdb 
rpmquery : local
repoquery : remote


sample .repo file in /etc/yum.repos.d
`[repo_id_1.0.0_7] 
name=repo_id_1.0.0_7        #repo NAME
baseurl=http://dev-web-yum1.xxx.xxxxx.xxxxx.net/yum/top_dir/repo_id/1.0.0_7
gpgcheck=0
enabled=0 `


Disecting the RPM 

rpm : queries the local rpm db

* Get the name of installed packages 
`rpm -qa | grep -i "pkg_name"`

* List all installed files in the pkg_name
`rpm -ql pkg_name`

* List the installed package dependencies
`rpm -q --requires pk_name-*`

* YUM : Repository mgmt tool (Resolve dependency of diff pkg)
* RPM : Pkg mgr tool for local system


*find the packages from the specific repo

yum --disablerepo "*" --enablerepo "CentOS-6-Epel-x86_64" list available 

* http://www.slashroot.in/yum-repository-and-package-management-complete-tutorial

##### References :
* http://www.itforeveryone.co.uk/rpm-build-hudson-jenkins.html
* http://fedoraproject.org/wiki/Packaging:Guidelines
* http://docs.fedoraproject.org/en-US/Fedora_Draft_Documentation/0.1/html/RPM_Guide/index.html
* https://fedoraproject.org/wiki/How_to_create_an_RPM_package?rd=PackageMaintainers/CreatingPackageHowTo
* https://fedoraproject.org/wiki/How_to_create_an_RPM_package?rd=PackageMaintainers/CreatingPackageHowTo
* http://www.ucs.cam.ac.uk/support/unix-support/talks/rpmbuild/files/rpmbuild.pdf
* http://freshrpms.net/docs/fight/
* http://docs.fedoraproject.org/en-US/Fedora_Draft_Documentation/0.1/html/Packagers_Guide/sect-Packagers_Guide-Package_Design.html
TODO
http://www.itforeveryone.co.uk/rpm-build-hudson-jenkins.html
http://fedoraproject.org/wiki/Packaging:Guidelines
http://docs.fedoraproject.org/en-US/Fedora_Draft_Documentation/0.1/html/RPM_Guide/index.html
https://fedoraproject.org/wiki/How_to_create_an_RPM_package?rd=PackageMaintainers/CreatingPackageHowTo
https://fedoraproject.org/wiki/How_to_create_an_RPM_package?rd=PackageMaintainers/CreatingPackageHowTo
http://www.ucs.cam.ac.uk/support/unix-support/talks/rpmbuild/files/rpmbuild.pdf
http://freshrpms.net/docs/fight/
https://github.com/RHInception/git-branch-blacklist/blob/master/git-hooks/pre-receive




