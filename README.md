# Gensyn CodeAssist Kurulum Rehberi !

Gensyn maliyetinden dolayı sürece katılamayanlar için tamamen ücretsiz bir yöntem.
WSL + Docker + CodeAssist ile hiçbir ücret ödemeden Participation kasabilirsiniz.

---

## 1) Gerekli Paketlerin Güncellenmesi:

```bash
sudo apt update && sudo apt upgrade -y && sudo apt install -y screen curl iptables build-essential git wget lz4 jq make gcc nano automake autoconf tmux htop nvme-cli libgbm1 pkg-config libssl-dev libleveldb-dev tar clang bsdmainutils ncdu unzip
```

---

## 2) Docker Kurulumu:

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

## 3) Python Kurulumu:

```bash
sudo apt install -y python3 python3-pip python3-venv
python3 --version
```

---

## 4) UV Kurulumu:

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

Örnek Çıtkı:

---

## 7) HuggingFace Token Gir:

- Terminal senden HuggingFace token isteyecek.
- https://huggingface.co/settings/tokens Bağlantıya git.
- "Create New Token"a tıkla.
- "Write"a tıklayıp bir isim belirle ve token oluştur.
- Oluşturduğun tokeni terminalde istediği kısma gir ve enter yap. (Tokeni girdiğinde gözükmez)

Örnek Çıktı:

<img width="581" height="146" alt="image" src="https://github.com/user-attachments/assets/946e206f-0156-4002-992d-224530ea8fd2" />

---

## 8) Giriş Yap:

- Yükleme tamamlandığında tarayıcıdan şu bağlantıya gir:

[http://localhost:3000/](http://localhost:3000/)

- Arayüz açıldığında mail adresin ile giriş yap.

---

## 9) Kodları AI ile Çözdür:

Hızlı çözüm yöntemi:

1. ChatGPT’yi aç.
2. CodeAssist arayüzünün ekran görüntüsünü at.
3. “Bunu çöz” de.
4. Çıkan çözümü CodeAssist’e yapıştırıp "SUBMIT SOLUTION" butonuna bas.
5. Sıradaki soruya geç.

Bu şekilde hızlı ve basit biçimde Participation biriktirebilirsin.

![çöz](https://github.com/user-attachments/assets/d5d945ac-91c3-465b-92be-07c88c80f47c)

---

## 10) Eğitimi Tamamla:

Soruları çözdükten sonra,

* Terminale dön.
* `CTRL + C` yap.
* 5-6 dakikma içerisinde eğitim tamamlanmış olur.

- Participation’larını buradan takip edebilirsin: [https://dashboard.gensyn.ai/?application=CodeAssist](https://dashboard.gensyn.ai/?application=CodeAssist)

✅ Tamamlandığına Dair Örnek Çıktı:

<img width="1678" height="541" alt="image" src="https://github.com/user-attachments/assets/d3c162ff-eee3-422e-9b21-9e88cedc49f4" />

---

## Terminalden Çıkış Yapanlar - Yeniden Başlatmak İçin:

```bash
screen -r codeassist
```
```bash
cd ~/codeassist
uv run run.py
```

---

## Amaç

* AI eğitim sürecine katkı sağlamak,
* AI kullanarak verilen küçük kod problemlerini çözüyoruz ve Participation topluyoruz.
* Gensyn ekosistemine maliyetsiz şekilde dahil olmak

---

Hazırlayan: @UfukDegen Sorularınız için bana ulaşabilirsiniz.
