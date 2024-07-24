As a DevOps engineer, proficiency in Linux commands is essential for managing servers, deploying applications, and automating tasks. Here is a list of important Linux commands grouped by their functionality:

### File and Directory Management:
1. **Listing Files and Directories:**
   - `ls`: List directory contents.
   - `ls -l`: List directory contents in long format.
   - `ls -a`: List all files, including hidden files.
2. **Changing Directories:**
   - `cd directory_name`: Change to a specific directory.
   - `cd ..`: Move up one directory.
   - `cd ~`: Change to the home directory.
3. **Creating and Removing Directories:**
   - `mkdir directory_name`: Create a new directory.
   - `rmdir directory_name`: Remove an empty directory.
4. **Creating, Copying, and Moving Files:**
   - `touch file_name`: Create an empty file or update the timestamp of an existing file.
   - `cp source_file destination_file`: Copy a file.
   - `mv source_file destination_file`: Move or rename a file.
   - `rm file_name`: Remove a file.
   - `rm -r directory_name`: Remove a directory and its contents recursively.

### File Content and Manipulation:
1. **Viewing File Contents:**
   - `cat file_name`: Display file contents.
   - `less file_name`: View file contents page by page.
   - `head file_name`: Display the first few lines of a file.
   - `tail file_name`: Display the last few lines of a file.
   - `tail -f file_name`: Continuously monitor a file for new lines.
2. **Editing Files:**
   - `nano file_name`: Edit a file using the nano text editor.
   - `vi file_name`: Edit a file using the vi text editor.
   - `vim file_name`: Edit a file using the vim text editor.
3. **Searching and Finding Files:**
   - `grep 'pattern' file_name`: Search for a pattern in a file.
   - `find /path -name 'file_name'`: Search for a file by name.
   - `locate file_name`: Find a file by name using the locate database.
4. **Sorting and Counting:**
   - `sort file_name`: Sort the contents of a file.
   - `wc file_name`: Count lines, words, and characters in a file.
   - `wc -l file_name`: Count lines in a file.

### System Monitoring and Management:
1. **System Information:**
   - `uname -a`: Display system information.
   - `hostname`: Display or set the hostname.
   - `uptime`: Show how long the system has been running.
   - `who`: Show who is logged on.
2. **Process Management:**
   - `ps aux`: Display a list of running processes.
   - `top`: Display real-time system and process information.
   - `htop`: Interactive process viewer (requires installation).
   - `kill process_id`: Terminate a process by its PID.
   - `kill -9 process_id`: Forcefully terminate a process.
   - `pkill process_name`: Kill processes by name.
3. **Disk Usage:**
   - `df -h`: Display disk space usage in a human-readable format.
   - `du -sh directory_name`: Display the size of a directory and its contents.
4. **Network Management:**
   - `ifconfig`: Display or configure network interfaces.
   - `ip addr`: Display IP address information.
   - `ping host`: Check network connectivity to a host.
   - `netstat -tuln`: List listening ports and associated programs.
   - `ss -tuln`: Display listening ports and sockets.
   - `traceroute host`: Trace the route packets take to a network host.
5. **Package Management:**
   - **Debian/Ubuntu:**
     - `apt-get update`: Update the package list.
     - `apt-get upgrade`: Upgrade installed packages.
     - `apt-get install package_name`: Install a package.
     - `apt-get remove package_name`: Remove a package.
   - **Red Hat/CentOS:**
     - `yum update`: Update all packages.
     - `yum install package_name`: Install a package.
     - `yum remove package_name`: Remove a package.
     - `dnf update`: Update all packages (for newer Fedora/CentOS).
     - `dnf install package_name`: Install a package.
     - `dnf remove package_name`: Remove a package.

### User and Permission Management:
1. **User Management:**
   - `adduser user_name`: Add a new user.
   - `userdel user_name`: Delete a user.
   - `passwd user_name`: Change a user's password.
2. **Group Management:**
   - `groupadd group_name`: Create a new group.
   - `groupdel group_name`: Delete a group.
   - `usermod -aG group_name user_name`: Add a user to a group.
3. **Permissions:**
   - `chmod permissions file_name`: Change file permissions.
   - `chown user_name file_name`: Change file ownership.
   - `chgrp group_name file_name`: Change file group ownership.

### Advanced Commands and Utilities:
1. **Archiving and Compression:**
   - `tar -cvf archive_name.tar directory_name`: Create a tar archive.
   - `tar -xvf archive_name.tar`: Extract a tar archive.
   - `gzip file_name`: Compress a file using gzip.
   - `gunzip file_name.gz`: Decompress a gzip file.
   - `zip archive_name.zip file_name`: Create a zip archive.
   - `unzip archive_name.zip`: Extract a zip archive.
2. **Cron Jobs and Scheduling:**
   - `crontab -e`: Edit the current user's cron jobs.
   - `crontab -l`: List the current user's cron jobs.
   - `cron syntax`: `* * * * * command_to_execute`
     - `minute hour day month day_of_week command_to_execute`
3. **SSH and Remote Access:**
   - `ssh user@host`: Connect to a remote host via SSH.
   - `scp file_name user@host:/path`: Copy a file to a remote host.
   - `rsync -avz source/ user@host:/path`: Synchronize files between local and remote systems.
4. **Log Management:**
   - `tail -f /var/log/syslog`: Continuously monitor the system log.
   - `tail -f /var/log/messages`: Continuously monitor the messages log.
   - `less /var/log/secure`: View security-related logs.

### Scripting and Automation:
1. **Basic Shell Scripting:**
   - `#!/bin/bash`: Start a Bash script.
   - `echo "Hello, World!"`: Print to the console.
   - `variable_name=value`: Define a variable.
   - `if [ condition ]; then ... fi`: Conditional statements.
   - `for item in list; do ... done`: Loop through items.
   - `function_name() { ... }`: Define a function.

### Common Tools:
1. **Text Processing:**
   - `awk`: Pattern scanning and processing language.
   - `sed`: Stream editor for filtering and transforming text.
2. **Version Control:**
   - `git clone https://github.com/user/repo.git`: Clone a Git repository.
   - `git add .`: Add changes to the staging area.
   - `git commit -m "message"`: Commit changes.
   - `git push`: Push changes to the remote repository.

### Docker Commands:
1. **Docker Basics:**
   - `docker build -t image_name .`: Build a Docker image from a Dockerfile.
   - `docker run -d --name container_name image_name`: Run a Docker container in detached mode.
   - `docker ps`: List running containers.
   - `docker stop container_name`: Stop a running container.
   - `docker rm container_name`: Remove a container.
   - `docker images`: List Docker images.
   - `docker rmi image_name`: Remove a Docker image.
2. **Docker Compose:**
   - `docker-compose up -d`: Start services defined in a `docker-compose.yml` file in detached mode.
   - `docker-compose down`: Stop and remove services defined in a `docker-compose.yml` file.

### Kubernetes Commands:
1. **Kubectl Basics:**
   - `kubectl get pods`: List all pods.
   - `kubectl get services`: List all services.
   - `kubectl get nodes`: List all nodes.
   - `kubectl describe pod pod_name`: Describe a pod.
   - `kubectl logs pod_name`: View logs for a pod.
   - `kubectl apply -f config.yaml`: Apply a configuration from a YAML file.
   - `kubectl delete -f config.yaml`: Delete resources defined in a YAML file.
2. **Managing Deployments:**
   - `kubectl rollout status deployment/deployment_name`: Check the rollout status of a deployment.
   - `kubectl scale deployment/deployment_name --replicas=num`: Scale a deployment to a specified number of replicas.
   - `kubectl set image deployment/deployment_name container_name=image_name`: Update the image of a deployment.

### Monitoring and Logging:
1. **System Monitoring:**
   - `top`: Display real-time system and process information.
   - `htop`: Interactive process viewer.
   - `vmstat`: Report virtual memory statistics.
   - `iostat`: Report CPU and I/O statistics.
2. **Log Analysis:**
   - `journalctl`: Query and

 display messages from the systemd journal.
   - `dmesg`: Print or control the kernel ring buffer.

### Networking:
1. **Network Configuration:**
   - `ip addr`: Show IP addresses.
   - `ip link`: Show and manipulate network interfaces.
   - `ip route`: Show and manipulate routing tables.
2. **Network Diagnostics:**
   - `ping host`: Test connectivity to a host.
   - `traceroute host`: Trace the route packets take to a network host.
   - `netstat -tuln`: List listening ports and associated programs.
   - `ss -tuln`: Display listening ports and sockets.
   - `curl url`: Transfer data from or to a server.
   - `wget url`: Non-interactive network downloader.

### File Transfer:
1. **scp (Secure Copy Protocol):**
   - `scp file_name user@host:/path`: Copy a file to a remote host.
   - `scp user@host:/path/file_name .`: Copy a file from a remote host.
2. **rsync (Remote Sync):**
   - `rsync -avz source/ user@host:/path`: Synchronize files between local and remote systems.
   - `rsync -avz user@host:/path source/`: Synchronize files from a remote system to local.

As a DevOps engineer working in a Windows environment, you should be familiar with various PowerShell and Command Prompt (CMD) commands. Here’s a comprehensive list of essential Windows commands categorized by functionality:

### File and Directory Management:
1. **Listing Files and Directories:**
   - `dir`: List directory contents.
2. **Changing Directories:**
   - `cd directory_name`: Change to a specific directory.
   - `cd ..`: Move up one directory.
   - `cd \`: Change to the root directory.
3. **Creating and Removing Directories:**
   - `mkdir directory_name`: Create a new directory.
   - `rmdir directory_name`: Remove an empty directory.
   - `rmdir /s /q directory_name`: Remove a directory and its contents recursively.
4. **Creating, Copying, and Moving Files:**
   - `type nul > file_name`: Create an empty file.
   - `copy source_file destination_file`: Copy a file.
   - `move source_file destination_file`: Move or rename a file.
   - `del file_name`: Delete a file.
   - `xcopy source_directory destination_directory /E /I`: Copy directories and subdirectories.

### File Content and Manipulation:
1. **Viewing File Contents:**
   - `type file_name`: Display file contents.
   - `more file_name`: View file contents page by page.
2. **Editing Files:**
   - `notepad file_name`: Open a file in Notepad.
3. **Searching and Finding Files:**
   - `findstr "pattern" file_name`: Search for a pattern in a file.
   - `dir /s /p file_name`: Search for a file by name.
4. **Sorting and Counting:**
   - `sort file_name`: Sort the contents of a file.
   - `find /c "text" file_name`: Count occurrences of a text string in a file.

### System Monitoring and Management:
1. **System Information:**
   - `systeminfo`: Display detailed system information.
   - `hostname`: Display the hostname of the system.
   - `whoami`: Display the current user.
2. **Process Management:**
   - `tasklist`: Display a list of running processes.
   - `taskkill /PID process_id /F`: Terminate a process by its PID.
   - `taskkill /IM process_name /F`: Terminate a process by its name.
3. **Disk Usage:**
   - `fsutil volume diskfree c:`: Display disk space usage.
4. **Network Management:**
   - `ipconfig`: Display IP address information.
   - `ping host`: Check network connectivity to a host.
   - `netstat -an`: Display network connections and listening ports.
   - `tracert host`: Trace the route packets take to a network host.
5. **Service Management:**
   - `net start service_name`: Start a service.
   - `net stop service_name`: Stop a service.
   - `sc query service_name`: Query the status of a service.

### Package Management:
1. **Windows Package Manager (winget):**
   - `winget search package_name`: Search for a package.
   - `winget install package_name`: Install a package.
   - `winget upgrade`: Upgrade all installed packages.
   - `winget uninstall package_name`: Uninstall a package.

### User and Permission Management:
1. **User Management:**
   - `net user user_name /add`: Add a new user.
   - `net user user_name /delete`: Delete a user.
   - `net user user_name new_password`: Change a user's password.
2. **Group Management:**
   - `net localgroup group_name /add`: Create a new group.
   - `net localgroup group_name user_name /add`: Add a user to a group.
   - `net localgroup group_name user_name /delete`: Remove a user from a group.
3. **Permissions:**
   - `icacls file_name /grant user_name:(permissions)`: Change file permissions.
   - `icacls file_name /remove user_name`: Remove file permissions.

### Advanced Commands and Utilities:
1. **Archiving and Compression:**
   - `compress -z file_name`: Compress a file.
   - `expand file_name`: Decompress a file.
2. **Task Scheduling:**
   - `schtasks /create /tn "TaskName" /tr "C:\Path\to\script.bat" /sc daily /st 09:00`: Create a scheduled task.
   - `schtasks /delete /tn "TaskName"`: Delete a scheduled task.
3. **SSH and Remote Access:**
   - `ssh user@host`: Connect to a remote host via SSH.
   - `scp file_name user@host:/path`: Copy a file to a remote host.
4. **Log Management:**
   - `Get-EventLog -LogName System -Newest 10`: Display the last 10 system log entries.
   - `wevtutil qe System /c:10 /f:text`: Display the last 10 system log entries in text format.

### PowerShell-Specific Commands:
1. **File and Directory Management:**
   - `Get-ChildItem`: List directory contents.
   - `Set-Location path`: Change directory.
   - `New-Item -Path path -ItemType Directory`: Create a new directory.
   - `Remove-Item -Path path`: Remove a directory or file.
   - `Copy-Item -Path source -Destination destination`: Copy a file or directory.
   - `Move-Item -Path source -Destination destination`: Move or rename a file or directory.
2. **File Content and Manipulation:**
   - `Get-Content file_name`: Display file contents.
   - `Set-Content -Path file_name -Value "text"`: Write text to a file.
   - `Add-Content -Path file_name -Value "text"`: Append text to a file.
   - `Select-String -Path file_name -Pattern "pattern"`: Search for a pattern in a file.
3. **System Monitoring and Management:**
   - `Get-Process`: Display a list of running processes.
   - `Stop-Process -Id process_id`: Terminate a process by its PID.
   - `Get-Service`: Display a list of services.
   - `Start-Service -Name service_name`: Start a service.
   - `Stop-Service -Name service_name`: Stop a service.
   - `Get-NetIPAddress`: Display IP address information.
   - `Test-Connection -ComputerName host`: Check network connectivity to a host.
   - `Get-EventLog -LogName System`: Display system log entries.
4. **User and Permission Management:**
   - `New-LocalUser -Name user_name`: Add a new user.
   - `Remove-LocalUser -Name user_name`: Delete a user.
   - `Add-LocalGroupMember -Group group_name -Member user_name`: Add a user to a group.
   - `Remove-LocalGroupMember -Group group_name -Member user_name`: Remove a user from a group.
   - `Get-Acl -Path file_name`: Display file permissions.
   - `Set-Acl -Path file_name -AclObject acl_object`: Change file permissions.
5. **Advanced Commands and Utilities:**
   - `Compress-Archive -Path file_name -DestinationPath archive_name.zip`: Compress a file.
   - `Expand-Archive -Path archive_name.zip -DestinationPath path`: Decompress a file.
   - `Register-ScheduledTask -Action (New-ScheduledTaskAction -Execute "Path\to\script.ps1") -Trigger (New-ScheduledTaskTrigger -Daily -At 9am) -TaskName "TaskName"`: Create a scheduled task.
   - `Unregister-ScheduledTask -TaskName "TaskName" -Confirm:$false`: Delete a scheduled task.

### Docker Commands:
1. **Docker Basics:**
   - `docker build -t image_name .`: Build a Docker image from a Dockerfile.
   - `docker run -d --name container_name image_name`: Run a Docker container in detached mode.
   - `docker ps`: List running containers.
   - `docker stop container_name`: Stop a running container.
   - `docker rm container_name`: Remove a container.
   - `docker images`: List Docker images.
   - `docker rmi image_name`: Remove a Docker image.
2. **Docker Compose:**
   - `docker-compose up -d`: Start services defined in a `docker-compose.yml` file in detached mode.
   - `docker-compose down`: Stop and remove services defined in a `docker-compose.yml` file.

### Kubernetes Commands:
1. **Kubectl Basics:**
   - `kubectl get pods`: List all pods.
   - `kubectl get services`: List all services.
   - `kubectl get nodes`: List all nodes.
   - `kubectl describe pod pod_name`: Describe a pod.
   - `kubectl logs pod_name`: View logs for a pod.
   - `kubectl apply -f config.yaml`: Apply a configuration from a YAML file.
   - `kubectl delete -f config.yaml`: Delete resources defined in a YAML file.
2. **Managing Deployments:**
   - `kubectl rollout status deployment/deployment_name`: Check the rollout status of a deployment.
   - `kubectl scale deployment/deployment_name --replicas=num`: Scale a deployment to a specified number of replicas.
   - `kubectl set image deployment/deployment_name container_name=image_name`: Update the image of a deployment.

### Monitoring and Logging:
1. **System Monitoring:**
   - `tasklist

`: Display a list of running processes.
   - `Get-Process`: Get a list of running processes.
   - `typeperf "\Processor(_Total)\% Processor Time" -si 5`: Display CPU usage.
2. **Event Logs:**
   - `Get-EventLog -LogName Application`: Display application event log entries.
   - `wevtutil qe Application /c:10 /f:text`: Display the last 10 application log entries in text format.
3. **Network Monitoring:**
   - `netstat -an`: Display network connections and listening ports.
   - `Get-NetTCPConnection`: Display TCP connections.

### Version Control (Git):
1. **Git Basics:**
   - `git clone https://repository_url.git`: Clone a Git repository.
   - `git status`: Check the status of your working directory and staging area.
   - `git add .`: Add changes to the staging area.
   - `git commit -m "commit message"`: Commit changes to the repository.
   - `git push`: Push changes to a remote repository.
   - `git pull`: Pull changes from a remote repository.
2. **Branch Management:**
   - `git branch branch_name`: Create a new branch.
   - `git checkout branch_name`: Switch to a different branch.
   - `git merge branch_name`: Merge changes from one branch into the current branch.

