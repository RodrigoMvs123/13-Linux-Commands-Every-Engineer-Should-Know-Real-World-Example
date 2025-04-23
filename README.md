#### 13 Linux Commands Every Engineer Should Know Real World Example

- https://www.youtube.com/watch?v=CLh2ACdXNbc

## Set up Linux Environment

Download Docker

- https://docs.docker.com/desktop/setup/install/windows-install/ 

Terminal 

> Tags ( linux-tutorial)

```
docker pull techworldwithnana/youtube:linux-tutorial
docker run -it techworldwithnana/youtube:linux-tutorial
```

Linux Commands 

Terminal
```
uname 
> 
 Linux
```

Use Linux commands to debug and solve issues

Terminal
```
pwd // Print working directory
>
 /root
```

Terminal
```
cd // Change directory
cd /var/log/application

pwd
> 
 /var/log/application
```

Terminal
```
ls // List files and directories
access.log   error.log    system.log 

ls -l // Long listing format
> 
 total 3
> -rw-r--r-- 1 root root 0 Oct  1 00:00 access.log
> -rw-r--r-- 1 root root 0 Oct  1 00:00 error.log
> -rw-r--r-- 1 root root 0 Oct  1 00:00 system.log
```

Terminal
```
cat // Concatenate and display file content
cat error.log
> 
 2023-10-01 00:00:00 ERROR: Something went wrong

cat error.log | grep ERROR // Filter lines containing "ERROR"
> 
  2023-10-01 00:00:00 ERROR: Something went wrong
  2023-10-01 00:00:01 ERROR: Another error occurred

cat error.log | grep Error > error.txt // Redirect output to a file
ls
> 
 access.log   error.log    system.log   error.txt

ls -l
> 
 total 4
> -rw-r--r-- 1 root root 0 Oct  1 00:00 access.log
> -rw-r--r-- 1 root root 0 Oct  1 00:00 error.log
> -rw-r--r-- 1 root root 0 Oct  1 00:00 system.log
> -rw-r--r-- 1 root root 0 Oct  1 00:00 error.txt

cat error.txt
> 
 2023-10-01 00:00:00 ERROR: Something went wrong
 2023-10-01 00:00:01 ERROR: Another error occurred
```

Terminal
```
cp // Copy files and directories
cp error.txt /root/db_error.txt // Copy error.txt to db_error.txt
ls /root
> 
 db_error.txt

cat /root/db_error.txt 
> 
 2023-10-01 00:00:00 ERROR: Something went wrong
 2023-10-01 00:00:01 ERROR: Another error occurred
```

Terminal
```
cat error.txt | grep "connection refused"
> 
 2023-10-01 00:00:00 ERROR: Something went wrong
 2023-10-01 00:00:01 ERROR: Another error occurred

cat error.txt | grep "connection refused" | wc -l // Count lines containing "connection refused"
> 
 0
```

Terminal
```   
find . -name "*.conf" // Search for files and directories
> 
 ./config.conf
 ./settings.conf

find / -name "*.conf" | wc -l // Count files and directories
> 
 2

find / -name "*.conf" | grep db
> 
  /db_config.conf
  /db_settings.conf

find / -name "*.conf*" | grep db // Search for files and directories with "db" in the name
> 
  /db_config.conf
  /db_settings.conf
  /db_config_backup

cd /etc/application 
cat db.conf
> 
  database_host=localhost
  database_port=5432
  database_name_production_db
  max_connections=100
  timeout=30
  retry_attempts=3
``` 

Terminal
``` 
diff db.conf db.conf.backup // Compare two files
>
  1c1
  < database_port=5433
  ---
  > database_port=5432
```

Terminal
```
curl https://google.com // Fetch content from a URL
> 
  <!DOCTYPE html>
  <html lang="en">
  <head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Google</title>
  </head>
  <body>
  <h1>Welcome to Google</h1>
  </body>
  </html>

curl http://localhost:5432 // Fetch content from a local server
> 
  <!DOCTYPE html>
  <html lang="en">
  <head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Local Server</title>
  </head>
  <body>
  <h1>Welcome to Local Server</h1>
  </body>
  </html>

curl -I http://localhost:5432
> 
  HTTP/1.1 200 OK
  Date: Mon, 01 Oct 2023 00:00:00 GMT
  Server: Apache/2.4.41 (Ubuntu)
  Content-Type: text/html; charset=UTF-8
  Content-Length: 1234
```

Terminal  
```
cat db.conf | grep database_host // Filter lines containing "database_host"
> 
  database_host=localhost 
  database_port=5432
  database_name=production_db
  max_connections=100
  timeout=30
  retry_attempts=3

vim db.conf // Open file in Vim editor
> 
  database_host=localhost
  database_port=5432
  database_name=production_db
  max_connections=100
  timeout=30
  retry_attempts=3
~
~
~
~
~
~
~

i // Insert mode
> 
  database_host=localhost
  database_port=5432
  database_name=production_db
  max_connections=100
  timeout=30
  retry_attempts=3
~
~
~
~
~
~
~
~
~
~
~
--INSERT -- W10: Warning. Changing a readonly file

esc // Exit insert mode
:q! // Quit Vim without saving changes
```

Terminal  
```
ls -l 
> 
 total 4  
> -rw-r--r-- 1 root root 0 Oct  1 00:00:00 access.log
> -rw-r--r-- 1 root root 0 Oct  1 00:00:00 error.log
> -rw-r--r-- 1 root root 0 Oct  1 00:00:00 system.log
> -rw-r--r-- 1 root root 0 Oct  1 00:00:00 error.txt

chmod 444 db.conf // Change file permissions
ls -l
> -r--r--r-- 1 root root 0 Oct  1 00:00:00 db.conf  

chmod 777 db.conf // Change file permissions
ls -l
> -rwxrwxrwx 1 root root 0 Oct  1 00:00:00 db.conf

chmod 666 db.conf // Change file permissions
ls -l
> -rw-rw-rw- 1 root root 0 Oct  1 00:00:00 db.conf

chmod 600 db.conf // Change file permissions
ls -l 
> -rw------- 1 root root 0 Oct  1 00:00:00 db.conf

vim db.conf // Open file in Vim editor
> 
  database_host=localhost
  database_port=5432
  database_name=production_db
  max_connections=100
  timeout=30
  retry_attempts=3
~
~
~ 
~
~
~
~
~
~

i // Insert mode
> 
  database_host=localhost
  database_port=5432
  database_name=production_db
  max_connections=100
  timeout=30
  retry_attempts=3
~
~
~
~
~
~
~

esc // Exit insert mode
:wq // Save and quit Vim

cat db.conf // Display file content
> 
  database_host=localhost
  database_port=5432
  database_name=production_db
  max_connections=100
  timeout=30
  retry_attempts=3  

exit // Exit terminal

ls 
> 
 Applications
 Demo-projects
 Desktop
 Documents
 Downloads

uname
> 
 Linux

chmod 400 db.conf // Change file permissions
ls -l
> -r-------- 1 root root 0 Oct  1 00:00:00 db.conf
```













