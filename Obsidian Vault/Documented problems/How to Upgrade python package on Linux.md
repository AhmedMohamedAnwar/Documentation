#### Your first think
```bash
sudo apt update 
sudo apt install -y python3.X.X
```
##### If the above commands give you error like that 
```bash
Reading package lists... Done
Building dependency tree       
Reading state information... Done
E: Unable to locate package python3.12
E: Couldn't find any package by glob 'python3.12'
```

------------------------------------------------------------------------
#### So you can make this solution 
- Go to this website https://www.python.org/downloads/                                                                      then download the Linux version 

- Then unzip & use this commands 
```bash
tar -xvf Python-3.12.13.tgz
# 
cd Python-3.12.13
# 
./configure \  
	--prefix=/opt/python/Python-3.12.13\  
	--enable-shared \  
	--enable-optimizations \  
	--enable-ipv6 \  
	LDFLAGS=-Wl,-rpath=/opt/python/Python-3.12.13/lib,--disable-new-dtags
# Install pyhon
make  
sudo make install
# verify installation 
/opt/python/Python-3.12.13/bin/Python-3.12.13 --version
# To make this the default python version
cd /opt/python/Python-3.12.13/bin  
sudo ln -s Python-3.12.13 python  
echo "PATH=/opt/python/Python-3.12.13/bin/:$""PATH" >> ~/.bashrc  
source ~/.bashrc
```

#### Visit this website to see full documented way
https://medium.com/@lupiel/installing-python-from-a-tgz-file-a-step-by-step-guide-4cf5f4a17a86
