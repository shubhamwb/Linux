Level 1 — Basics



* pwd - present working directory - shows the current directory
* clear - clear the terminal
* ls - list files and directories



&#x20;ls      List files              

&#x20;ls -l   Detailed listing        

&#x20;ls -a   Show hidden files       

&#x20;ls -h   Human-readable sizes    

&#x20;ls -la  Detailed + hidden files 



* cd - Change directory

&#x20;cd /var/log	-- go to a specific directory

&#x20;cd ..  	-- go to one directory back

&#x20;cd \~ 		-- go to home directory

&#x20;cd -		-- go to previous directory



* mkdir - create a new directory	
* touch - create an empty file
* cat - display the file contents
* less - Read large files 

&#x20;	use case - Useful for large logs because it doesn't dump the entire file onto the terminal.



* head - shows the beginning of a file 

&#x09;use - useful for viewing the first few lines of a file or output

* tail - shows the ending of a file

&#x09;use - useful for viewing the last few lines of a file or output

&#x09;IMP - **tail -f application.log** - This continuously displays new log entries.



* cp - copy files or directories from one location to another.
* mv - move files or directories from one location to another or rename them within the same directory or across directories
* rm - deletes files and directories from the filesystem permanently





* find - finds a file in a directory
* grep - searches inside the file 
* wc - counts lines, words, characters, and bytes in files or from standard input
* sort - organises text files or input data in various orders.
* uniq - filters out adjacent duplicate lines
* cut - extracts specific sections from each line of a file or standard input, based on byte position, character position, or field delimiter
* awk - search, filter, and manipulate structured data
* sed - to search and replace in a file 
* pipe (|) - send output from one command to another 





Redirection

* >  - overwrite 
* >> - append
* <  - input





System Information

* date 		- displays the date
* uname		- shows Linux/Kernel information
* hostname 	- shows the server name
* cat /etc/os-release - shows OS information
* uptime	- shows how long the server has been running, Number of users, Load average
* whoami 	- shows the current user

&#x09;use: Useful when working on EC2/Linux servers and checking which user you're logged in as.



* free		- checks memory usage
* df		- checks filesystem/disk usage
* du 		- checks directory size



Process Management

* ps - shows the processes
* top - shows the real-time CPU, Memory, Processes, and load
* kill - terminates the process





Service / Systemd

* system - service operations like start, restart, enable, disable



* ip addr - show IP addresses
* ip route - show routes



* ping - check network connectivity
* curl - check the HTTP status



* wget - download the file
* ss -tuln  - check listening port



* nslookup - check DNS resolution
* dig - Detailed DNS information



* ssh - connect to server
* scp - copy file from local to server



* chmod - change file and directory permissions
* chown - change owner or group of file and directory

























* 

