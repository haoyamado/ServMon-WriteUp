# ServMon-WriteUp
This repositories contains is Write-Up for machines as ServMon from HackTheBox

# 1. Recon
### Here we going to Reconnaisance:
### Scanning ports (open and close).
### Let's saving this script as start_scan.sh:
      ports=$(nmap -p- --min-rate=1000  -T4 10.10.10.184 | grep ^[0-9] | cut -d '/' -f 1 | tr '\n' ',' | sed s/,$//)
      nmap -sC -sV -p$ports 10.10.10.184

### Next open terminal and run us script: 
      sudo bash start_scan.sh > results.txt

### After scanning and writing results in outfile, we're analysing.

