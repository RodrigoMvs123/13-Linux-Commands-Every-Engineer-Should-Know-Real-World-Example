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
```





