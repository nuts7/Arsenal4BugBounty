# JS files Enumeration

% JS files enumeration, Find JS files

## Find JavaScript Files with assetfinder and gau
#plateform/linux #target/remote #cat/RECON
https://github.com/tomnomnom/assetfinder

```bash
assetfinder --subs-only <HOST> | gau | egrep -v '(.css|.png|.jpeg|.jpg|.svg|.gif|.wolf)' | while read url; do vars=$(curl -s $url | grep -Eo "var [a-zA-Zo-9_]+" | sed -e 's, 'var','"$url"?',g' -e 's/ //g' | grep -v '.js' | sed 's/.*/&=xss/g'):echo -e "\e[1;33m$url\n" "\e[1;32m$vars"; done
```

## Extract Endpoints from JavaScript file
#plateform/linux #target/remote #cat/RECON

```bash
cat <FILE.js> | grep -oh "\"\/[a-zA-Z0-9_/?=&]*\"" | sed -e 's/^"//' -e 's/"$//' | sort -u
```
