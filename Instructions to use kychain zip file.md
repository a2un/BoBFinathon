The following instructions are for windows machines (x86 or x64) only:

follow the instructions to [Download and install](https://www.multichain.com/download-install/) multichain zip
Add the multichain install folder path to [environment variables](https://superuser.com/questions/737542/how-can-i-add-a-program-path-to-the-windows-environment-variables-for-easy-comma)


[Download and install]() wamp server
If it throws error for vcredist dlls, uninstall wamp completely.
[Download and install]() vc redist in a sequential order depending on your architecture (x86 or x64)

Install Python2.7
Install VC for Python 2.7
[Donwload and install]() pip
Install pycrypto using pip

Download multichain explorer from [here]() as a zip
Unzip the contents
Open cmd and run the command "cd <path>/<to>/multichain-explorer-folder"
run the command "python setup.py install".This will install Mce.abe Python module

Once you have confirmed that all the installations are complete and proper:
download kychain.zip from this repository

Unzip the contents into the folder you wish to keep

Open a cmd instance and run the following commands;
cd <path>/<to>/kychain/servernminer
start /b multichaind -datadir=. kychain -daemon

if all is well, the blockchain node will be accessible at <your-ip-addrss>:4765

Now open another cmd instance and rum the following commands:
cd <path>/<to>/kychain/node1
start /b multichaind -datadir=. kychain@<your-ip-addrss>:4765 -daemon

If node1 doesn't havd connect permissions to the blockchain, follow thr instructions [here]().here node "servernminer' is the genesis node


copy  <path>/<to>/kychaindemo and paste the folder and its contents as is into <path>/<to>/wamp-instsllstion/www/

Launch wamp server

in your browswr go to "localhost/kychaindemo'
If all is well you'll aee a website similar to [this](http://52.172.209.229/multichain-web-demo/)

Launch another cmd instance and run the following commands:
cd  <path>/<to>/kychainexplorer/
python -m Mce.abe --config kycchain.conf

If all goes well, in your browser the multichain explorer will launch at http://localhost:2750/ with a green label connection phrase agains the chain name
