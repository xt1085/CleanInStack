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
# 安装 zlib 库
apt update -y && apt install zlib1g-dev -y
tar -xzf cleaninstack-full.tar.gz
./oneinstack/install.sh
```

Reference: https://github.com/oneinstack/oneinstack/issues/487

nginx make -j1 && make install
memory THREAD=1
check_os
