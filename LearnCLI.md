#lsof (Linux)
	$lsof -p pid # Get which file was opened by pid.
	$lsof /var/run/sendmail.pid # Get which process opened this file.
	$lsof | grep deleted ; cat /proc/pid/fd/dddd > /tmp/sample # Get file already been deleted.
	$lsof -i :80 # Get process using port 80
	$lsof -i @192.168.1.10 # Get process communicating with 192.168.1.10
