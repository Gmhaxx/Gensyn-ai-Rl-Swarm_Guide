<div align="center">

# 💻 Gensyn-ai-Rl-Swarm_Guide {Mac/Linux} 💻

</div>


# Device/System Requirements 🖥️

![image](https://github.com/user-attachments/assets/594d0847-362b-4ea6-9e61-8590105421c8)

❌❌The Node Wont work on low Specs Devices, It can Cause System Crashing if u try on Low Specs Devices

* Open Your Vps

```
ssh username@ip
```

# Pre-Requirements 🛠

# Install Python and Other Tools

* For Linux/Wsl

```
sudo apt update && sudo apt install -y python3 python3-venv python3-pip curl wget screen git lsof

```

* For Mac

```
brew install python
```

Check Version

```
python3 --version
```


# Install Node.js , npm & yarn

* For Linux/Wsl

```
curl -fsSL https://deb.nodesource.com/setup_20.x | sudo -E bash - && sudo apt update && sudo apt install -y nodejs
```

* Install Yarn (linux)

```
curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -
```

```
echo "deb https://dl.yarnpkg.com/debian/ stable main" | sudo tee /etc/apt/sources.list.d/yarn.list > /dev/null
```

```
sudo apt update && sudo apt install -y yarn
```


* For Mac

```
brew install node && corepack enable && npm install -g yarn
```

* Check version (Linux/Mac)

```
node -v
```
```
npm -v
```

```
yarn -v
```


<div align="center">

# 👨🏻‍💻 Start The Node (Linux/Mac) 

</div>


* 1️⃣ Clone RL-SWARM Repo

```
git clone https://github.com/gensyn-ai/rl-swarm.git
```


* 2️⃣ Create a screen session (vps)

```
screen -S gensyn
````

* 3️⃣ Navigate to rl-swarm

```
cd rl-swarm
```

* 4️⃣ Create & Activate a Virtual Environment

```
python3 -m venv .venv
source .venv/bin/activate
```

* 5️⃣ Install Left-over dependencies

```
cd modal-login
```

```
yarn install
```

```
yarn upgrade &&  yarn add next@latest &&  yarn add viem@latest
```

* 6️⃣ Run the swarm Node 🚀

```
cd ..
```

```
./run_rl_swarm.sh
```

- After Running the Above command it will promt `Would you like to connect to the Testnet? [Y/n]` Enter `Y`

- A web Pop-Up will appear, It will ask u to Login ( if no web pop-up then u have to paste this on ur brower `http://localhost:3000/` 


- Now Login With Your Email Id, Enter OTP and back to ur Terminal/Wsl? ( VPS users check FAQ1)

![image](https://github.com/user-attachments/assets/1fed4b08-4ec4-44de-868c-b2d314cd2a02)


- Now U can see A `ORG_ID` On ur Terminal..Save it!



* Now It will promt `Would you like to push models you train in the RL swarm to the Hugging Face Hub? [y/N]` Enter `N`

![image](https://github.com/user-attachments/assets/b63da75d-389a-4ded-9c4e-cd23804d94ef)



![image](https://github.com/user-attachments/assets/35321942-1aa3-47f1-92a3-dae9881b64cd)

Here we go🚀

Its Done ✅

It will Generate Logs Soon🙌


* Detach from `screen session` (vps)

Use `Ctrl + A` and then press `D`

* Attach to gensyn Screen to see Logs

```
screen -r gensyn
```



<div align="center">

#  🛠 FAQ & Troubleshoot 🛠

</div>


# 1️⃣ How to Login or access  http://localhost:3000/ in VPS? 📶

* Open a new Terminal and login ur vps 

* Allow Incoming connection on VPS

```
sudo apt install ufw -y
sudo ufw allow 3000/tcp
```

* Enable ufw

```
sudo ufw enable
```

* Go to `chrome://flags/#unsafely-treat-insecure-origin-as-secure` (use secondary chrome profile)


![image](https://github.com/user-attachments/assets/d95e7e44-2325-4dd5-93a7-62baab27c7d1)

* Enter your public ip and port (3000) here (check ss )

`http://PUBLIC-IP:3000`

![Screenshot 2025-04-05 015227](https://github.com/user-attachments/assets/3fc367a3-969b-41f4-9be5-4918e941733a)

* `Enabled` It

* To apply changes It will promt you to `Relaunch` 

* Now Open 2nd tab in chrome and enter your `PUBLIC_IP:3000` in this formate

* Now follow Login!
 
* Done!✅



# 2️⃣ Solution of OOM errors on MacBook (Memory/Cpu limit)

* Open -
 ```
nano ~/.zshrc
```

* Paste in the file

```
export PYTORCH_MPS_HIGH_WATERMARK_RATIO=0.0
export PYTORCH_ENABLE_MPS_FALLBACK=1
```
* Reload with

```
  source ~/.zshrc
```

# 3️⃣ How to get the Node Name?

* Check the image below to get your Node id!

![image](https://github.com/user-attachments/assets/728c6401-75c8-43b4-973c-e9d515c4b453)

# 4️⃣ Save your `swarm.pem` file (for future login)

```
nano ~/rl-swarm/swarm.pem
```



Follow official Docs for more info and Errors!

https://github.com/gensyn-ai/rl-swarm/tree/brian-address-cpu-only-crashes?tab=readme-ov-file#troubleshooting

👉 Join TG for more Updates: https://telegram.me/cryptogg

If U have any issue then open a issue on this repo or Dm me on TG~

Thank U! 👨🏻‍💻 Happy Coding💗

