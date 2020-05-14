# ServMon-WriteUp
This repositories contains is Write-Up for machines as ServMon from HackTheBox
<img src="https://www.hackthebox.eu/storage/avatars/2bc1a8dc04b09b8ac2db694f25ccf051.png" width="600">
# 1. Recon
### Here we going to Reconnaisance:
### Scanning ports (open and close).
### Let's saving this script as start_scan.sh:
      ports=$(nmap -p- --min-rate=1000  -T4 10.10.10.184 | grep ^[0-9] | cut -d '/' -f 1 | tr '\n' ',' | sed s/,$//)
      nmap -sC -sV -p$ports 10.10.10.184

### Next open terminal and run us script: 
      sudo bash start_scan.sh > results.txt

### After scanning and writing results in outfile, we're analysing.

### port 21/tcp is FTP. Let's connect to FTP:
      sudo ftp 10.10.10.184
      login: anonymous
      passwords: e-mail or any words
      
### Successful! We're connect to FTP.
### Next we going to directory Users, where sign two users: Nathan and Nadine.
      cd Nadine
      dir
      Confedential.txt
### File Confidential.txt saying us, what file Passwords locate on Desktop Nathan's 

