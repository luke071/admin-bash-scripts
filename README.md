# Bash scripts with the scope of the EX200 material
## 1. Script that displays information about hostname, system boot time, system memory usage, disk space usage and logged in users.  
Granting permissions to execute:  
chmod +x script.sh  
Running the script:  
./script.sh  

```bash
#!/bin/bash  

echo "****SYSTEM INFORMATION****"  
hostname  
uptime  
free -h  
df -h  
echo "****LOGGED IN USERS****"  
who  
```

# Bask scripts with the scope of the EX294 material