# git compilation
```shell
tar -Jxvf git-2.25.1.tar.xz
cd git-2.25.1/
make configure
./configure --prefix=/usr
make all doc info
sudo make install install-doc install-html install-info
```
