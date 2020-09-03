# Fake Seeder

------

How to...

 1. Put the seeds(.torrent files) in the torrent directory!
 2. Modify the User-Agent and peer_id prefixes for torrents.py.
 3. Install the appropriate library via `pip3 install requests`.
 4. Exec `python3 seedmage.py`

How to get UA and peer_id, please refer to [my website][1].


  [1]: https://www.taterli.com "my website"
  
-----

# seed.sh  添加到定时任务
  18  */2  *  *   *    cd /root/ && bash seed.sh &
```
#!/bin/bash

# 获得 python3 seedmage.py &  程序的 pid
pid=$(ps -ef | awk '/[s]eedmage.py/{print $2}')

if [[ -z "${pid}" ]]; then
   cd /root/fakeseeder/  &&  python3 seedmage.py &
fi

if [[ ! -z "${pid}" ]]; then
   echo ":: seedmage.py  working ..."
fi
```
### 升级部分debian系统 到 python3.7环境
```
apt install -y  build-essential autoconf libtool automake make
wget http://192.227.248.118/py37.tgz
tar xf py37.tgz
cd Python-3.7.2/
make install
```
