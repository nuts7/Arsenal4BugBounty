# Subdomain Enumeration

% subdomains Enumeration

## Get subdomains from IPs
#plateform/linux #target/remote #cat/RECON
https://github.com/SpiderLabs/HostHunter

```bash
hosthunter.py <IPs_IN.txt> > <SUBDOMAINS_OUT.txt>
```

## Get subdomains from crt.sh
#plateform/linux #target/remote #cat/RECON
https://crt.sh/

```bash
curl -s "https://crt.sh/?q=%25.<domain.tld>&output=json" | jq -r '.[].name_value' | sed 's/\*\.//g' | sort -u
```

## Get valid subdomains from subfinder via HTTPX
#plateform/linux #target/remote #cat/RECON
https://github.com/projectdiscovery/subfinder

```bash
subfinder -d <domain.tld> -silent | httpx -title -tech-detect -status-code
```

## Get valid subdomains from assetfinder via httprobe
#plateform/linux #target/remote #cat/RECON
https://github.com/tomnomnom/assetfinder

```bash
assetfinder <domain.tld> | httprobe
```

## Fuzz subdomains via ffuf
#plateform/linux #target/remote #cat/RECON
https://github.com/ffuf/ffuf

```bash
ffuf -u https://<domain.tld> -w <wordlist.txt> -v | grep "| URL |" | awk '{print $4}'
```
