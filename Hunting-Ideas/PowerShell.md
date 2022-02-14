# Commands With Potential Malicious Usage

```PowerShell
# Systeminfo
systeminfo
hostname 

# Especially good with hotfix info
wmic qfe get Caption,Description,HotFixID,InstalledOn

# What users/localgroups are on the machine?
net users
net localgroups
net user hacker

# To see domain groups if we are in a domain
net group /domain
net group /domain 
# Network information
ipconfig /all
route print
arp -A

# To see what tokens we have 
whoami /priv

# Recursive string scan
findstr /spin "password" *.*

# Running processes
tasklist /SVC

# Network connections
netstat -ano

# Search for writeable directories
dir /a-r-d /s /b

### Some good one-liners
# Obtain the path of the executable called by a Windows service (good for checking Unquoted Paths):
sc query state= all | findstr "SERVICE_NAME:" >> a & FOR /F "tokens=2 delims= " %i in (a) DO @echo %i >> b & FOR /F %i in (b) DO @(@echo %i & @echo --------- & @sc qc %i | findstr "BINARY_PATH_NAME" & @echo.) & del a 2>nul & del b 2>nul

# current domain info
[System.DirectoryServices.ActiveDirectory.Domain]::GetCurrentDomain()

# domain trusts
([System.DirectoryServices.ActiveDirectory.Domain]::GetCurrentDomain()).GetAllTrustRelationships()

# current forest info
[System.DirectoryServices.ActiveDirectory.Forest]::GetCurrentForest()

# get forest trust relationships
([System.DirectoryServices.ActiveDirectory.Forest]::GetForest((New-Object System.DirectoryServices.ActiveDirectory.DirectoryContext('Forest', 'forest-of-interest.local')))).GetAllTrustRelationships()

# get DCs of a domain
nltest /dclist:offense.local
net group "domain controllers" /domain

# get DC for currently authenticated session
nltest /dsgetdc:offense.local

# get domain trusts from cmd shell
nltest /domain_trusts

# get user info
nltest /user:"spotless"

# get DC for currently authenticated session
set l

# get domain name and DC the user authenticated to
klist

# get all logon sessions. Includes NTLM authenticated sessions
klist sessions

# kerberos tickets for the session
klist

# cached krbtgt
klist tgt

# whoami on older Windows systems
set u
```


### Resources
- [red team cheatsheet](https://0xsp.com/offensive/red-ops-techniques/red-team-cheatsheet)
