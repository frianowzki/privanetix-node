

# Privasea Privanetix Node (Incentivized)

- Minimum System Requirements

- Operating System (OS): Ubuntu (Recommended)

- CPU Architecture: amd64 (x86 architecture)

- Storage: 100GB available storage

- Memory (RAM): 4GB RAM

- Processor: 6 cores

#
#

✨ install Docker (bisa diskip yang udah keinstall Docker)

```
source <(wget -O - https://raw.githubusercontent.com/frianowzki/installer/main/docker.sh)
```
```
sudo groupadd docker && sudo usermod -aG docker $(whoami) && newgrp docker
```

✨ Pull Privasea Docker Image

```
docker pull privasea/acceleration-node-beta:latest
```

✨ Create Privasea folder

```
mkdir -p ~/privasea/config && cd ~/privasea
```

✨ Installation & node wallet generation

```
docker run --rm -it -v "$HOME/privasea/config:/app/config" privasea/acceleration-node-beta:latest ./node-calc new_keystore
```

- set password dan diingat buat akses kita nanti dan copy address yang barusan di generate.

✨ Pindah keystore ke folder baru (backup juga sekalian)

```
mv $HOME/privasea/config/UTC--* $HOME/privasea/config/wallet_keystore
```

✨ Lanjut ke: https://deepsea-beta.privasea.ai/privanetixNode
#

✨ Connect wallet node/testnet buat jadi Operator
#

✨ Claim faucet Arb Sepolia & Privasea DeepSea Beta
#

✨ Lanjut: https://deepsea-beta.privasea.ai/privanetixNode > create new > isi nama node & fill address yang tadi di generate > stake TPRAI 
#

✨ Balik lagi ke Terminal, run ini

```
KEYSTORE_PASSWORD=password-ente && docker run -d --name privanetix-node -v "$HOME/privasea/config:/app/config" -e KEYSTORE_PASSWORD=$KEYSTORE_PASSWORD privasea/acceleration-node-beta:latest
```

- ganti password-ente pake password yang tadi dibikin.
#
Done, refresh web sekarang status udah online

#
#
✨ Check logs:

```
docker logs -f privanetix-node
```

✨ Stop & delete node

```
docker stop privanetix-node && docker rm privanetix node
```
```
rm -rf privasea
```
#
Yang ga bisa run node tapi mau partisipasi bisa stake di punya ane 
#
Name: 
```
friodrops
```
Node ID: 
```
304
```
#
More info dimari: 

https://privasea.gitbook.io/user-node-usage-documentation

https://www.privasea.ai/privanetix-node
