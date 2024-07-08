Certainly! Here is a comprehensive list of essential commands for DevOps engineers, combining both Linux and Windows environments:

## General Commands:

### File and Directory Management:

#### Linux:
- `ls`: List directory contents.
- `cd directory_name`: Change to a specific directory.
- `mkdir directory_name`: Create a new directory.
- `rm file_name`: Remove a file.
- `rm -r directory_name`: Remove a directory and its contents recursively.
- `cp source_file destination_file`: Copy a file.
- `mv source_file destination_file`: Move or rename a file.

#### Windows:
- `dir`: List directory contents.
- `cd directory_name`: Change to a specific directory.
- `mkdir directory_name`: Create a new directory.
- `rmdir /s /q directory_name`: Remove a directory and its contents recursively.
- `copy source_file destination_file`: Copy a file.
- `move source_file destination_file`: Move or rename a file.
- `del file_name`: Delete a file.

### File Content and Manipulation:

#### Linux:
- `cat file_name`: Display file contents.
- `less file_name`: View file contents page by page.
- `grep "pattern" file_name`: Search for a pattern in a file.
- `sort file_name`: Sort the contents of a file.
- `wc file_name`: Count lines, words, and characters in a file.

#### Windows:
- `type file_name`: Display file contents.
- `more file_name`: View file contents page by page.
- `findstr "pattern" file_name`: Search for a pattern in a file.
- `sort file_name`: Sort the contents of a file.
- `find /c "text" file_name`: Count occurrences of a text string in a file.

## System Monitoring and Management:

### System Information:

#### Linux:
- `uname -a`: Display system information.
- `top`: Display tasks and system performance.
- `uptime`: Show how long the system has been running.

#### Windows:
- `systeminfo`: Display detailed system information.
- `hostname`: Display the hostname of the system.
- `whoami`: Display the current user.

### Process Management:

#### Linux:
- `ps aux`: Display a list of running processes.
- `kill PID`: Terminate a process by its PID.
- `pkill process_name`: Terminate a process by its name.

#### Windows:
- `tasklist`: Display a list of running processes.
- `taskkill /PID process_id /F`: Terminate a process by its PID.
- `taskkill /IM process_name /F`: Terminate a process by its name.

### Disk Usage:

#### Linux:
- `df -h`: Display disk space usage.
- `du -sh directory_name`: Display the size of a directory.

#### Windows:
- `fsutil volume diskfree c:`: Display disk space usage.

### Network Management:

#### Linux:
- `ifconfig`: Display or configure network interfaces.
- `ping host`: Test connectivity to a host.
- `netstat -tuln`: List listening ports and associated programs.
- `curl url`: Transfer data from or to a server.

#### Windows:
- `ipconfig`: Display IP address information.
- `ping host`: Check network connectivity to a host.
- `netstat -an`: Display network connections and listening ports.
- `curl url`: Transfer data from or to a server.
- `tracert host`: Trace the route packets take to a network host.

### User and Permission Management:

#### Linux:
- `useradd user_name`: Add a new user.
- `userdel user_name`: Delete a user.
- `passwd user_name`: Change a user's password.
- `chown user_name file_name`: Change file owner.
- `chmod permissions file_name`: Change file permissions.

#### Windows:
- `net user user_name /add`: Add a new user.
- `net user user_name /delete`: Delete a user.
- `net user user_name new_password`: Change a user's password.
- `net localgroup group_name /add`: Create a new group.
- `net localgroup group_name user_name /add`: Add a user to a group.
- `icacls file_name /grant user_name:(permissions)`: Change file permissions.

### Service Management:

#### Linux:
- `systemctl start service_name`: Start a service.
- `systemctl stop service_name`: Stop a service.
- `systemctl status service_name`: Check the status of a service.

#### Windows:
- `net start service_name`: Start a service.
- `net stop service_name`: Stop a service.
- `sc query service_name`: Query the status of a service.

### Archiving and Compression:

#### Linux:
- `tar -czvf archive_name.tar.gz directory_name`: Create a compressed archive.
- `tar -xzvf archive_name.tar.gz`: Extract a compressed archive.

#### Windows:
- `compress -z file_name`: Compress a file.
- `expand file_name`: Decompress a file.

### Task Scheduling:

#### Linux:
- `crontab -e`: Edit cron jobs.
- `crontab -l`: List cron jobs.

#### Windows:
- `schtasks /create /tn "TaskName" /tr "C:\Path\to\script.bat" /sc daily /st 09:00`: Create a scheduled task.
- `schtasks /delete /tn "TaskName"`: Delete a scheduled task.

### SSH and Remote Access:

#### Linux:
- `ssh user@host`: Connect to a remote host via SSH.
- `scp file_name user@host:/path`: Copy a file to a remote host.

#### Windows:
- `ssh user@host`: Connect to a remote host via SSH.
- `scp file_name user@host:/path`: Copy a file to a remote host.

### Log Management:

#### Linux:
- `tail -f /var/log/syslog`: Continuously monitor a log file.
- `journalctl -u service_name`: Display logs for a specific service.

#### Windows:
- `Get-EventLog -LogName System -Newest 10`: Display the last 10 system log entries.
- `wevtutil qe System /c:10 /f:text`: Display the last 10 system log entries in text format.

## Docker Commands:

#### Both Linux and Windows:
- `docker build -t image_name .`: Build a Docker image from a Dockerfile.
- `docker run -d --name container_name image_name`: Run a Docker container in detached mode.
- `docker ps`: List running containers.
- `docker stop container_name`: Stop a running container.
- `docker rm container_name`: Remove a container.
- `docker images`: List Docker images.
- `docker rmi image_name`: Remove a Docker image.
- `docker-compose up -d`: Start services defined in a `docker-compose.yml` file in detached mode.
- `docker-compose down`: Stop and remove services defined in a `docker-compose.yml` file.

## Kubernetes Commands:

#### Both Linux and Windows:
- `kubectl get pods`: List all pods.
- `kubectl get services`: List all services.
- `kubectl get nodes`: List all nodes.
- `kubectl describe pod pod_name`: Describe a pod.
- `kubectl logs pod_name`: View logs for a pod.
- `kubectl apply -f config.yaml`: Apply a configuration from a YAML file.
- `kubectl delete -f config.yaml`: Delete resources defined in a YAML file.
- `kubectl rollout status deployment/deployment_name`: Check the rollout status of a deployment.
- `kubectl scale deployment/deployment_name --replicas=num`: Scale a deployment to a specified number of replicas.
- `kubectl set image deployment/deployment_name container_name=image_name`: Update the image of a deployment.

## Monitoring and Logging:

### System Monitoring:

#### Linux:
- `top`: Display tasks and system performance.
- `htop`: An interactive process viewer.

#### Windows:
- `tasklist`: Display a list of running processes.
- `Get-Process`: Get a list of running processes.

### Event Logs:

#### Linux:
- `journalctl`: Query and display messages from the systemd journal.
- `dmesg`: Print or control the kernel ring buffer.

#### Windows:
- `Get-EventLog -LogName Application`: Display application event log entries.
- `wevtutil qe Application /c:10 /f:text`: Display the last 10 application log entries in text format.

### Network Monitoring:

#### Linux:
- `netstat -tuln`: List listening ports and associated programs.
- `ss -tuln`: Display listening ports and sockets.

#### Windows:
- `netstat -an`: Display network connections and listening ports.
- `Get-NetTCPConnection`: Display TCP connections.

## Version Control (Git):

### Both Linux and Windows:
- `git clone https://repository_url.git`: Clone a Git repository.
- `git status`: Check the status of your working directory and staging area.
- `git add .`: Add changes to the staging area.
- `git commit -m "commit message"`: Commit changes to the repository.
- `git push`: Push changes to a remote repository.
- `git pull`: Pull changes from a remote repository.
- `git branch branch_name`: Create a new branch.
- `git checkout branch_name`: Switch to a different branch.
- `git merge branch_name`: Merge changes from one branch into the current branch.

