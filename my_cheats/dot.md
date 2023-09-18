# Remote Windows Commands

#plateform/linux  #target/remote  #cat/RECON 

## Find Domain Controllers
```
nslookup _ldap._tcp.dc._msdcs
```
## Add computer to domain
```
addcomputer.py -computer-name '<computername>$' -computer-pass '<computerpass>' -dc-host <dc> -domain-netbios <domain> '<domain>\<user>:'<password>''
```

#plateform/linux  #cat/RECON  
## CrossLinked
Naming format:
{f}.{last}              = j.smith
{first}.{last}           = john.smith
CMP\{first}{l}          = CMP\johns
{f}{last}@company.com  = jsmith@company.com 
```
crosslinked -f 'namingformat. -j2 'company name on linkedin'
```

#plateform/linux  #target/remote  #cat/RECON 

# Local Windows Commands

## Determine Function Level of Domain
#plateform/windows #target/local #cat/RECON 
```
dsquery * "DC=splpharma,DC=com" -scope base -attr msDS-Behavior-Version ntMixedDomain
```
## Clear RDP session cache
```
rwinsta <session_ID>
```
# Local Linux Commands
## PCredz
#plateform/linux
```
python3 /opt/PCredz/Pcredz -i <eth_adapter> -v
```
## PyPyKatz
#plateform/linux #cat/CRACKING/PASSWORD 
```
pypykatz lsa minidump <dmp_file>
```
## DPAT password report - cleartext
#plateform/linux #cat/CRACKING/PASSWORD 
```
dpat.py -n <ntds> -c <potfile>
```
## DPAT password report - sanitized
#plateform/linux #cat/CRACKING/PASSWORD 
```
dpat.py -n <ntds> -c <potfile> -s
```
## max.py password report - cleartext
#plateform/linux #cat/CRACKING/PASSWORD 
```
python3 max.py -u <neo4j_username> - <neo4j_password> dpat -n <ntds> -c <potfile> -o max_report_clear --html
```
## max.py password report - sanitized
#plateform/linux #cat/CRACKING/PASSWORD 
```
python3 max.py -u <neo4j_username> - <neo4j_password> dpat -n <ntds> -c <potfile> -o max_report_sanitized --html -s
```
## Crack LM Hashes
#plateform/linux #cat/CRACKING/PASSWORD 
```
hashcat.exe -m 3000 -a 3 customer.ntds -1 ?a ?1?1?1?1?1?1?1 --increment
```
## Add route to another VLAN
#plateform/linux 
```
ip route add <target_subnet> via <gateway_ip> dev <eth_adapter>
```
## Determine WAF with identYwaf 
#plateform/linux 
```
python3 identYwaf.py --random-agent <url>
```
