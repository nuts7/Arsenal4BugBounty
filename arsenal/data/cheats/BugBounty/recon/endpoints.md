# Endpoints Enumeration

% endpoints Enumeration

## Get endpoints from AlienVault's Open Threat Exchange, the Wayback Machine, and Common Crawl via gau
#plateform/linux #target/remote #cat/RECON
https://github.com/lc/gau

```bash
gau <domain.tld>
```

## Fuzz endpoints with feroxbuster
#plateform/linux #target/remote #cat/RECON

```bash
feroxbuster -w `fzf-wordlists` -u "https://<domain.tld>/"
```

## Fuzz endpoints from APK
#plateform/linux #target/remote #cat/RECON
https://github.com/iBotPeaches/Apktool

```bash
apktool d <app.apk> -o uberApk;grep -Phro "(https?://)[\w\.-/]+[\"'\`]" uberApk/ | sed 's#"##g' | anew | grep -v "w3\|android\|github\|http://schemas.android\|google\|http://goo.gl"
```
