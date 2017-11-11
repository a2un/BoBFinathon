The following instructions are for windows 7 machines (x86 or x64) only:

* Follow the instructions to [Download and install](https://www.multichain.com/download-install/) multichain zip(version 1.0.1, Protocol	10009)
* Add the multichain install folder path to [environment variables](https://superuser.com/questions/737542/how-can-i-add-a-program-path-to-the-windows-environment-variables-for-easy-comma)


* [Download and install](https://excellmedia.dl.sourceforge.net/project/wampserver/WampServer%202/Wampserver%202.5/wampserver2.5-Apache-2.4.9-Mysql-5.6.17-php5.5.12-64b.exe) wamp server
* If it throws error for vcredist dlls, uninstall wamp completely.
* [Download and install](http://forum.wampserver.com/read.php?2,138295) vc redist in a sequential order depending on your architecture (x86 or x64). Install WAMP again.

* [Download and Install](https://www.python.org/ftp/python/2.7/python-2.7.amd64.msi) Python2.7
* [Download and Install](https://download.microsoft.com/download/7/9/6/796EF2E4-801B-4FC4-AB28-B59FBF6D907B/VCForPython27.msi) VC for Python 2.7
* [Download and install](https://stackoverflow.com/questions/4750806/how-do-i-install-pip-on-windows#12476379) pip
* Install pycrypto using pip
`pip install pycrypto`

* Download multichain explorer from [here](https://github.com/MultiChain/multichain-explorer) as a zip
* Unzip the contents
* Open cmd and run the command <br/> `cd <path>/<to>/multichain-explorer-folder`
* run the command <br/> `python setup.py install`<br/> This will install Mce.abe Python module

Once you have confirmed that all the installations are complete and proper:
* download [kychaindemo.zip](https://github.com/a2un/BoBFinathon/raw/master/kychaindemo.zip) from this repository

* Unzip the contents into the folder you wish to keep

* Open a cmd instance and run the following commands:<br/>
`cd <path>/<to>/kychain/servernminer`<br/>
`start /b multichaind -datadir=. kychain -daemon`

If all is well, the blockchain node will be accessible at `<your-ip-addrss>:4765`

* Now open another cmd instance and rum the following commands:
`cd <path>/<to>/kychain/node1`<br/>
`start /b multichaind -datadir=. kychain@<your-ip-addrss>:4765 -daemon`

* If node1 doesn't havd connect permissions to the blockchain, follow the instructions under "2. Connecting to a blockchain" while using the "-datadir=." right after the "multichain-cli" (command as explained) [here](https://www.multichain.com/getting-started).here node "servernminer' is the genesis node

* copy  `<path>/<to>/kychaindemo` and paste the folder and its contents as is into `<path>/<to>/wamp-installation/www/`

Launch wamp server

* In your browswer go to "localhost/kychaindemo' If all is well you'll see a website similar to [this](http://52.172.209.229/multichain-web-demo/)

* Launch another cmd instance and run the following commands:<br />
`cd  <path>/<to>/kychainexplorer/`<br/>
`python -m Mce.abe --config kycchain.conf`

If all goes well, in your browser the multichain explorer will launch at http://localhost:2750/ with a green label connection phrase against the chain name and it will look like [this](http://52.172.209.229:2750/)
