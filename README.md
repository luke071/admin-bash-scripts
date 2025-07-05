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

## 2. Creating a script to add users from a csv file. 
Additional assumptions:  
- the password must be changed upon first login;  
- the maximum password validity period is 60 days;  
- a warning will be displayed 7 days before the password expires.  

File users.csv  

```csv
username,password
fbaggins,T29GETEi6
sgamgee,pg06RhJXC
mbrandybuck,iWpMa1mmu
```

Script create _new _users.sh

```bash
#!/bin/bash

CSV_FILE="users.csv"

# Checking if file exists
if [[ ! -f "$CSV_FILE" ]]; then
    echo "File $CSV_FILE does not exist."
    exit 1
fi

# We skip the first line and process each line
tail -n +2 "$CSV_FILE" | while IFS=',' read -r username password; do
    if id "$user_name" &>/dev/null; then
        echo "User $user_name already exists."
    else
        useradd -m "$user_name"
        echo "$user_name:$password" | chpasswd
        chage -d 0 "$user_name"
        chage -M 60 "$user_name"
        chage -W 7 "$user_name"
        echo "User created: $user_name"
    fi
done

```



# Bask scripts with the scope of the EX294 material


