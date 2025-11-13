# Gensyn CodeAssist Kurulum Rehberi !

Gensyn maliyetinden dolayı sürece katılamayanlar için tamamen ücretsiz bir yöntem.
WSL + Docker + CodeAssist ile hiçbir ücret ödemeden Participation kasabilirsiniz.

---

## 1) Gerekli Paketlerin Güncellenmesi

```bash
sudo apt update && sudo apt upgrade -y && sudo apt install -y screen curl iptables build-essential git wget lz4 jq make gcc nano automake autoconf tmux htop nvme-cli libgbm1 pkg-config libssl-dev libleveldb-dev tar clang bsdmainutils ncdu unzip
```

---

## 2) Docker Kurulumu

```bash
sudo apt update -y && sudo apt upgrade -y && \
for pkg in docker.io docker-doc docker-compose podman-docker containerd runc; do sudo apt-get remove -y $pkg; done && \
sudo apt-get update -y && \
sudo apt-get install -y ca-certificates curl gnupg && \
sudo install -m 0755 -d /etc/apt/keyrings && \
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg && \
sudo chmod a+r /etc/apt/keyrings/docker.gpg && \
echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null && \
sudo apt update -y && sudo apt upgrade -y && \
sudo apt-get install -y docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin && \
sudo docker run --rm hello-world
```

---

## 3) Python Kurulumu

```bash
sudo apt install -y python3 python3-pip python3-venv
python3 --version
```

---

## 4) UV Kurulumu

```bash
curl -LsSf https://astral.sh/uv/install.sh | sh
export PATH="/root/.local/bin:$PATH"
```
```bash
uv --version
```

---

## 5) CodeAssist’i Klonla:

```bash
git clone https://github.com/gensyn-ai/codeassist.git
cd codeassist
```

---

## 6) Çalıştır:

```bash
sudo apt install -y screen
```
```bash
screen -S codeassist
```
```bash
cd ~/codeassist
uv run run.py
```

---

## 7) HuggingFace Token Gir

- Terminal senden HuggingFace token isteyecek.
- https://huggingface.co/settings/tokens Bağlantıya git.
- "Create New Token"a tıkla.
- "Write"a tıklayıp bir isim belirle ve token oluştur.
- Oluşturduğun tokeni terminalde istediği kısma gir ve enter yap. (Tokeni girdiğinde gözükmez)

---

## 8) Giriş Yap

- Yükleme tamamlandığında tarayıcıdan şu bağlantıya gir:

[http://localhost:3000/](http://localhost:3000/)

- Arayüz açıldığında mail adresin ile giriş yap.

---

## 9) Kodları AI ile Çözdür

Hızlı çözüm yöntemi:

1. ChatGPT’yi aç.
2. CodeAssist arayüzünün ekran görüntüsünü at.
3. “Bunu çöz” de.
4. Çıkan çözümü CodeAssist’e yapıştırıp "SUBMIT SOLUTION" butonuna bas.
5. Sıradaki soruya geç.

Bu şekilde hızlı ve basit biçimde Participation biriktirebilirsin.

---

## 10) Eğitimi Tamamla

Soruları çözdükten sonra:

* Terminale dön
* `CTRL + C` yap
* Eğitim tamamlanmış olur

- Participation’larını buradan takip edebilirsin: [https://dashboard.gensyn.ai/?application=CodeAssist](https://dashboard.gensyn.ai/?application=CodeAssist)

---

## Tekrar Başlatmak İçin

```bash
cd ~/codeassist
screen -S codeassist
uv run run.py
```

---

İstersen bu README'yi repo stiline göre daha kompakt veya daha detaylı hale de getirebilirim.
