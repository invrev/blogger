##File processing
####Show top # lines
* head -# <file_name>

####Show bottom n lines from file_name
* tail -n # <file_name>

####Given file split it with delim and extract columns
* cut -d 'delim' -f1,2

####Get the dump from url
* lynx -dump 'url'

#### Find the lines excluding pattern
* grep -v <pattern>
#### Count # of delims "|" from the file
* head -1 "txt" | awk -F'|' '{ print NF }'
#### Replace comma with new line 
* cat <file_name> | awk -F ',' '{for(i=1;i<=NF;i++) printf "%s\n", $i}'
* cat <file_name> | sed 's/,/\n/g' 
* sed 's/,/\n/g' -i <file_name> (in place editing )
* perl -ane 'print "Hello world"';
* perl -pi -w -e 's/SEARCH_FOR/REPLACE_WITH/g;' *.txt
* perl -pi -w -e 's/stupid/awesome/g;' ~/Desktop/*.txt
#### Replace dates (2010-12-31,2011-12-31,2012-12-31) to 4 from date_file in place 
* perl -p -i -e 's/201[0-2]-12-31/4/g' date_file (in-place)
* cat date_file | perl –p –e 's/201[0-2]-12-31/4/g;' > new_date_file

##System utils
#### find location of executable
* which <name_of_executable>

##Network utils
#### List out all the connection in listen state
* netstat -a | egrep 'Proto|LISTEN'
#### Monitor network traffic w/o SSH,UDP,ARP not to and from host x.x.x,x and dump the result in "cap.txt" 
* tcpdump -i eth0 -W cap.txt port not ssh and not udp and not arp and host not x.x.x,x
* tcpdump -i eth0 -w cap.pcap port not ssh and not udp and not arp and host not x.x.x,x

###Comman utils
#### Print all the directories (including hidden)
* find . -type d -print
#### Search all the files in the current directory for the content 'TriggerExpression' 
#### To handle spaces use 0 / output not contains new line and spaces
* find . -type f -print0 | xargs -0 grep 'TriggerExpression'
#### Do Not handle spaces
* find . -type f -print | xargs grep 'TriggerExpression'
#### Search the hello in all the .sh files
* find . -name "*.sh" | xargs grep "hello"


###BASH TODOs
#### Use sourcing 
#### Use shortcuts || && to save LOC
#### Use globbing

###RPMS
* yum --enablerepo=${_repo_name} install 
#### Run level check
* chkconfig --list jenkins
#### Query rpm repo 
* yum list | grep "pkg_name"
* yum list '*Libre*'
#### Remove package
* yum remove <pkg_name>
#### To list versions
* rpm -qa | grep \<executable_file>
* rpm -qa | grep libreoffice
* rpm -qf `which <executable_file>`

###TODOS RPM
Write the conservative path in spec file to avoid conflict in-short try to avoid
the use of regex in the spec file
