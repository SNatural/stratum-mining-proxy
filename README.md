stratum-mining-proxy
====================

Application providing HTTP/getwork protocol <--> Stratum and Stratum/LTC mining protocols bridge

Installation on Windows
-----------------------

1. Download official Windows binaries (EXE) from http://pool.itzod.ru/mining_proxy.exe or http://ltcmine.ru/mining_proxy.exe
2. Open downloaded file. It will open console window. Using default settings, proxy connects to Itzod's mining pool (or ltcmine pool, if -pa scrypt was specified)
3. If you want to connect to another pool or change other proxy settings, type "mining_proxy.exe --help" in console window.

Installation using Github on Debian/Ubuntu
-------------------------

1. sudo apt-get install -y git-core python-dev libssl-dev
2. git clone https://github.com/SNatural/stratum-mining-proxy.git
3. cd stratum-mining-proxy
4. sudo python distribute_setup.py

5. sudo apt-get install python-pip
6. sudo apt-get install python-autobahn
7. sudo pip install stratum
8. pip install --upgrade pip

9. sudo python setup.py develop

10. ./mining_proxy.py -o host -p port

If you want to connect to another pool or change other proxy settings, type ```./mining_proxy.py --help```.

If you want to update the proxy, type ```git pull``` in the package directory.

Compiling midstate C extension
------------------------------
For some really big operations using getwork interface of this proxy, you'll find
useful "midstatec" C extension, which significantly speeds up midstate calculations
(yes, plain python implementation is *so* slow). For enabling this extension,
just type "make" in midstatec directory. Proxy will auto-detect compiled extension
on next startup.

Contact
-------

This proxy is provided by Slush's mining pool at http://mining.bitcoin.cz. You can contact the author
by email info(at)bitcoin.cz or by IRC on irc.freenode.net in channel #stratum.

This proxy was modified to add support of Stratum/LTC mining protocol. Modifications implemented by LTCMine.ru and pool.itzod.ru minings pools administrator, you can ask your 
questions by email balthazar(at)yandex.ru or PM at btc-e.com exchange.
