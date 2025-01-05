Run HyperSpace tanpa GPU

1. Install Docker jika belum ada, kalau sudah ada bisa di skip
```
apt install docker.io -y
```

2. Pull Docker Image
```
docker pull ubuntu:22.04
```

3. Jalankan Docker Container
```
docker run -it --name aios ubuntu:22.04
exit
docker container start aios
```

4. Masuk ke dalam Container
```
docker container exec -it aios /bin/bash
```

5. Update Docker Ubuntu dan Install HyperSpace
```
cd && apt update && apt upgrade && apt install curl tmux -y
curl https://download.hyper.space/api/install | bash
source /root/.bashrc
```

6. Masuk ke tmux
```
tmux new -s aios
```

7. Start aios
```
aios-cli start
```
Setelah running, CTRL + B lalu D

8. Login
```
aios-cli hive login
```

9. Pilih Tier
```
aios-cli hive select-tier 5
```

10. Add Models
```
aios-cli models add hf:TheBloke/Mistral-7B-Instruct-v0.1-GGUF:mistral-7b-instruct-v0.1.Q4_K_S.gguf
```

11. Connect aios
```
aios-cli hive connect
```

12. Backup Pubkey + Privkey
```
aios-cli hive whoami
```

13. Cek Points
```
aios-cli hive points
```

Done, lanjut ngopi
