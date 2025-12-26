# nebula-alpine-builder

## Install instructions

### 1. Trust your GitHub signing key
```
sudo wget -O /etc/apk/keys/signing.rsa.pub \
$(curl -s https://api.github.com/repos/clayswreg/nebula-alpine-builder/releases/latest | grep "browser_download_url" | grep ".pub" | cut -d '"' -f 4)
```

### 2. Download all APKs from the latest release
```
curl -s https://api.github.com/repos/clayswreg/nebula-alpine-builder/releases/latest \
| grep "browser_download_url" | grep ".apk" | cut -d '"' -f 4 \
| xargs -n 1 wget
```

### 3. Install the packages
```
sudo apk add ./nebula-custom-*.apk
```
