> **Use at own risk**

File Downloaded from: https://www.dropbox.com/s/iampc7prd9y7cqf/oneinstack-full.tar.gz?dl=1    
MD5: `b2947bac8cb66d54fcd90d30e406598f`

Before installation, block the below domains at `/etc/hosts`:

```
0.0.0.0 mirrors.linuxeye.com
0.0.0.0 mirrors.oneinstack.com
```

## Installation

```bash
wget https://github.com/hifocus/CleanInStack/releases/download/0.0.0/cleaninstack-full.tar.gz
md5sum cleaninstack-full.tar.gz

MD5=$(md5sum cleaninstack-full.tar.gz | awk '{print $1}')
if [ "$MD5" != "b2947bac8cb66d54fcd90d30e406598f" ]; then
    echo "MD5 校验失败！当前值：$MD5"
    exit 1
fi
echo "MD5 校验正常：$MD5"

# Block Oneinstack untrusted domains
echo "0.0.0.0 mirrors.linuxeye.com" | sudo tee -a /etc/hosts
echo "0.0.0.0 mirrors.oneinstack.com" | sudo tee -a /etc/hosts
```

```
# if the result is b2947bac8cb66d54fcd90d30e406598f
apt update -y && apt install zlib1g-dev -y
tar -xzf cleaninstack-full.tar.gz
./oneinstack/install.sh
```


```
> /root/oneinstack/include/check_os.sh
sed -i 's/make -j ${THREAD}/make -j1/g' /root/oneinstack/include/nginx.sh
FILE=/root/oneinstack/include/memory.sh
grep -q '^THREAD=1$' $FILE || \
sed -i "/Swap=\`free -m | awk '\/Swap:\/{print \$2}'\`/a THREAD=1" $FILE
```

```
apt update
apt install -y lsof
include/check_sw.sh
config error parsing file failed
```

Reference: https://github.com/oneinstack/oneinstack/issues/487



