# 🚀 MINIMAL BACA

Automation bot for account registration and Stripe checkout with stealth browser support.

Supported environments:

* 💻 Windows (Development)
* ☁️ Ubuntu VPS (Production)

---

## 🧠 Overview

### Bot ini akan:

1. Membuat email (mail.tm)
2. Kirim magic link
3. Verifikasi akun
4. Checkout Stripe otomatis
5. Generate API key

---

# 💻 SETUP DI WINDOWS (DEVELOPMENT)

## 1. Install Python

Download:
https://www.python.org/downloads/

✔ centang **Add to PATH**

---

## 2. Clone / Extract Project

```bash
cd path\ke\project
```

---

## 3. Buat Virtual Environment

```bash
python -m venv venv
venv\Scripts\activate
```

---

## 4. Install Dependencies

```bash
pip install -r requirements.txt
```

---

## 5. Install Browser (WAJIB)

```bash
playwright install
```

---

## 6. Setup Data

### credits.txt

```text
4111111111111111|12/25|123
```

### proxies.txt (optional) | GAUSAH PAKE JUGA GAPAPA

```text
http://user:pass@ip:port
ip:port
```

---

## 7. Run Bot
### Generate API Key 
```bash
python main.py
```

### Create Agent
```bash
python main.py --register
```

---

# ☁️ SETUP DI VPS UBUNTU (PRODUCTION)

## 1. Login VPS

```bash
ssh root@IP_VPS
```

---

## 2. Install Dependencies

```bash
apt update && apt upgrade -y
apt install -y python3 python3-pip python3-venv git unzip
```

---

## 3. Upload Project

### Option A (recommended: git) | SKIP

```bash
git clone REPO_URL
cd project
```

### Option B (manual upload) | BISA SKIP

```bash
scp project.zip root@IP_VPS:/root/
unzip project.zip
cd project
```

---

## 4. Buat Virtual Environment

```bash
python3 -m venv venv
source venv/bin/activate
```

---

## 5. Install Python Dependencies

```bash
pip install --upgrade pip
pip install -r requirements.txt
```

---

## 6. Install Playwright (WAJIB)

```bash
playwright install
playwright install-deps
```

---

## 7. Jalankan Bot

```bash
python main.py --register
```

---

## 8. Jalankan di Background (Opsional)

```bash
apt install screen -y
screen -S bot
python main.py --register
```

Detach:

```
CTRL + A + D
```

---

# 🐳 Docker Deployment For VPS (Recomended)
### Build image
```bash
docker build -t blink-bot .
```

## Run container
```bash
docker run -it --rm blink-bot
```

## Run with volume (save results)
```bash
docker run -it --rm \
-v $(pwd)/result:/app/result \
blink-bot
```

## Run background (production)
```bash
docker run -d --name blinkbot \
-v $(pwd)/result:/app/result \
blink-bot
```

## Lihat log
```bash
docker logs -f blinkbot
```

## Stop / restart
```bash
docker stop blinkbot
docker start blinkbot
```

## Agent-Mode
### Buat liat api agent bisa ikutin step ini :
- buka https://mail.tm/en/
- Login email dan pw ada di accounts.json
- buka https://blink.new/sign-in
- Login dengan email yang sama
- Verif link nya di mail.tm

## ⚠️ PENTING

---

### ❗ VPS = Headless Mode

Tidak ada browser GUI → normal.

---

### ❗ CAPTCHA kemungkinan muncul

#### Penyebab:

* IP VPS (datacenter)
* terlalu banyak request

### Solusi:

* gunakan proxy residential
* tambahkan delay

---

## 🧠 TROUBLESHOOTING

### ❌ Module not found

```bash
pip install -r requirements.txt
```

---

### ❌ Playwright error

```bash
playwright install
```

---

### ❌ Stripe iframe tidak ditemukan

* tambah delay
* cek koneksi VPS

---

### ❌ Rate limit (magic link)

Normal → sudah ada retry di code

---

## 🎯 BEST PRACTICE

* Gunakan Windows untuk testing
* Gunakan VPS untuk production
* Gunakan proxy untuk scaling
* Jangan spam terlalu cepat

---

## ⚡ Disclaimer

Gunakan dengan bijak.
