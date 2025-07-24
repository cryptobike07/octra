# Octra Public Testnet

![testnet](https://github.com/user-attachments/assets/aa4f05f1-0f0a-41d0-8ed8-df215b340c46)

## Join Discord
https://discord.gg/octra

---

## Requirements
Linux Ubuntu OS
* **VPS**: You can use a linux VPS to follow the guide
* **Windows**: Install Linux Ubuntu using WSL by following this [guide](https://github.com/0xmoei/Install-Linux-on-Windows)
* **Codespace**: If you don't have VPS or Windows WSL, you can use [Github Codespace](https://github.com/codespaces), create a blank template and run your codes.

---

## Install dependecies
Install & Update Packages:
```
sudo apt update && sudo apt upgrade -y
sudo apt install screen curl iptables build-essential git wget lz4 jq make gcc nano automake autoconf tmux htop nvme-cli libgbm1 pkg-config libssl-dev libleveldb-dev tar clang bsdmainutils ncdu unzip libleveldb-dev  -y
```
Install Nodejs (Only VPS users)
```
sudo apt update
sudo curl -fsSL https://deb.nodesource.com/setup_22.x | sudo -E bash -
sudo apt install -y nodejs
node -v
npm install -g yarn
yarn -v
```

Tutorial on Setting up VPS.
1. Rent a VPS
VPS is (Virtual Private Server that runs 24/7)
“I’m using VPS in all my Linux NODES.”
Hardware Requirement:
Works with simple hardware — easy to get started but I can run it in my VPS3.
2. How to Run Octra Node using VPS?
Order Here: (Use the Link and Euro(€) For Discount)
https://www.jdoqocy.com/click-101100040-15022370
Click Cloud VPS(I used VPS 3 coz I run other Nodes here) > Region Any(I used Japan) > Storage Type 1200GB > Ubuntu v22.04> Log in Password (Don’t forget) > 6–8 settings default only > Click Next >
Fill up your details > Payment.
“I used Gotymebank or Maya(both vitual cards) link to Paypal(all are perfored in the website). I paid €23 or 1500+ pesos for first month(+ set up fee), second only €14 or 900+ pesos .”
Once Paid > Wait for the Email to Arrived > Follow instruction.
Setting up on Your Laptop/PC Windows:
Now you have your own VPS server.
Download putty.org > log in to your IP there.
After Connected, We can now Start.
Still Confuse? More Guide in VPS Access:
https://www.facebook.com/share/p/zhHCh3773653iXZF/
You have now your own Ubuntu(Linux Server) that runs 24/7 in other country. Let’s Navigate!

---

## Create wallet
### 1. Clone the repository
   ```bash
   git clone https://github.com/0xmoei/wallet-gen.git
   cd wallet-gen
   ```

### 2. Run the wallet generator webserver
   **Linux/macOS:**
   ```bash
   chmod +x ./start.sh
   ./start.sh
   ```


### 3. Open your browser
* **WSL/Linux/MAC users:**
  * Navigate to `http://localhost:8888` on browser

  
* **VPS users:**
  * 1- Open a new terminal
  * 2- Install **localtunnel**:
    ```
    npm install -g localtunnel
    ```
  * 3- Get a password:
    ```
    curl https://loca.lt/mytunnelpassword
    ```
  * The password is actually your VPS IP
  * 4- Get URL
    ```
    lt --port 8888
    ```
  * Visit the prompted url, and enter your password to access wallet generator page

--You can also visit http://YOURIP:8888 ; sample http://123.240.249.129:8888

### 4. Generate wallet
* Click "GENERATE NEW WALLET" and watch the real-time progress
* Save all the details of your Wallet

---

## Get Faucet
* Visit [Faucet page](https://faucet.octra.network/)
* Enter your address starting with `oct...` to get faucet
* If there is no faucet ask here: #for-token-sharing https://discord.gg/fSMq9eJCqx
* You can also get 1 octa every 24 hrs here https://oct-faucet.xme.my.id/ (Unofficial Faucet)

![image](https://github.com/user-attachments/assets/18597b40-eaad-434f-a026-cc4a56a6d1a8)

---

## Configure Octra CLI and Wallet

**1. Install Python**
```bash
sudo apt install python3 python3-pip python3-venv python3-dev -y
```

**2. Install CLI**
```bash
git clone https://github.com/octra-labs/octra_pre_client.git
cd octra_pre_client

python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt

cp wallet.json.example wallet.json
```

**3. Add wallet to CLI**
```bash
nano wallet.json
```
* Replace following values:
  * `private-key-here`: Privatekey with `B64` format
  * `octxxxxxxxx...`: Octra address starting with `oct...`


**4. Run CLI**
```bash
python3 -m venv venv
source venv/bin/activate
python3 cli.py
```
* This should open a Testnet UI

![image](https://github.com/user-attachments/assets/0ba1d536-4048-4899-a977-4517b2e522cd)

---

## Update CLI
After each new task, existing users must update their CLI

### Option A: Normal Update
Update git:
```bash
cd octra_pre_client
git pull origin main
```
* If you see an error about uncommitted changes (e.g., in `cli.py` or other files), stash your changes:
```bash
git stash
git pull origin main
```

Install requirements:
```
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```

In case you still got error in running the python program, follow the instruction below and repeat all the steps  

### Option B: Wipe and Reclone (Use if Option A fails or you want a clean setup)
Update git:

* Preserve your `wallet.json` file, wipe the repository, and reclone it:
```
mv $HOME/octra_pre_client/wallet.json $HOME/wallet.json
cd && rm -rf octra_pre_client && git clone https://github.com/octra-labs/octra_pre_client.git
mv $HOME/wallet.json $HOME/octra_pre_client/wallet.json
cd octra_pre_client
```

Install requirements:
```
python3 -m venv venv
source venv/bin/activate
pip install -r requirements.txt
```
---

## Testnet Tasks

## Run CLI
```bash
cd octra_pre_client
python3 -m venv venv
source venv/bin/activate
python3 cli.py
```

## Send transactions
* 1- Encrypt balance
* 2- Send private transaction to another address
  * You can send private transactions to my address: `oct2ZsFU4yh4ChaBgC1qHajJSPyd5DfG5UxdsK8MdbbZAAt`
  * Use [Octra Explorer](https://octrascan.io/) to find more octra addresses


---

## Wait for next steps
Stay tuned.
