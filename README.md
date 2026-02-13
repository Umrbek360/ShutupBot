# 🤖 ShutupBot - Telegram Moderatsiya Boti

<div align="center">

![Python](https://img.shields.io/badge/Python-3.11+-blue?style=for-the-badge&logo=python)
![Aiogram](https://img.shields.io/badge/Aiogram-3.22+-green?style=for-the-badge&logo=telegram)
![Railway](https://img.shields.io/badge/Railway-Deploy_ready-0B0D0E?style=for-the-badge&logo=railway)
![License](https://img.shields.io/badge/License-MIT-yellow?style=for-the-badge)

**Telegram guruhlarida taqiqlangan so'zlarni avtomatik ravishda nazorat qiluvchi aqlli moderatsiya boti**

[🚀 O'rnatish](#-o'rnatish) • [🚂 Railway deploy](#-railway-ga-deploy-qilish) • [⚙️ Sozlash](#️-sozlash) • [📖 Foydalanish](#-foydalanish) • [🔧 Xususiyatlar](#-xususiyatlar)

</div>

---

## 📋 Loyiha haqida

**ShutupBot** - bu Telegram guruhlarida taqiqlangan so'zlarni avtomatik ravishda aniqlab, foydalanuvchilarni progressiv jazo tizimi orqali nazorat qiluvchi aqlli moderatsiya boti. Bot foydalanuvchilarning xatti-harakatlarini 24 soat davomida kuzatib, har bir qoida buzish uchun mos darajada jazo beradi.

### 🎯 Asosiy maqsad
- Guruhlarda toza va madaniy muhit yaratish
- Taqiqlangan so'zlardan foydalanishni oldini olish
- Foydalanuvchilarni progressiv jazo tizimi orqali o'qitish
- Adminlarning ishini engillashtirish

---

## ✨ Xususiyatlar

### 🛡️ Aqlli Moderatsiya
- **Avtomatik aniqlash**: Taqiqlangan so'zlarni real vaqtda aniqlaydi
- **Xabar o'chirish**: Buzilgan xabarlarni avtomatik o'chiradi
- **Progressiv jazo**: Har bir qoida buzish uchun ortib boruvchi jazo muddati

### 📊 Progressiv Jazo Tizimi
| Qoida buzish soni | Jazo muddati | Tavsif |
|-------------|--------------|---------|
| 1-chi | 5 daqiqa | Birinchi ogohlantirish |
| 2-chi | 15 daqiqa | Ikkinchi ogohlantirish |
| 3-chi | 1 soat | Uchinchi ogohlantirish |
| 4-chi va undan keyin | 1 kun | Jiddiy jazo |

### 🔄 Avtomatik Tizim
- **24 soatlik kuzatuv**: Har bir foydalanuvchining qoida buzishlarini 24 soat davomida hisoblaydi
- **Avtomatik tozalash**: 24 soatdan keyin qoida buzishlar hisobini tozalaydi
- **Xabar o'chirish**: Blok tugagach, guruhdagi ogohlantirish xabarlarini avtomatik o'chiradi

### 💬 Xabar Tizimi
- **Shaxsiy ogohlantirish**: Har bir foydalanuvchiga shaxsiy xabar yuboradi
- **Guruh bildirishnomasi**: Guruhga qoida buzish haqida ma'lumot beradi
- **O'zbek tilida**: Barcha xabarlar o'zbek tilida

---

## 🚀 O'rnatish

### 📋 Talablar
- Python 3.11 yoki undan yuqori versiya
- Telegram Bot Token (BotFather dan olingan)
- Git

### 🔧 O'rnatish qadamlari

1. **Loyihani klonlash**
```bash
git clone https://github.com/NodirUstoz/ShutupBot.git
cd ShutupBot
```

2. **Virtual muhit yaratish**
```bash
python -m venv venv
# Windows uchun:
venv\Scripts\activate
# Linux/Mac uchun:
source venv/bin/activate
```

3. **Kerakli kutubxonalarni o'rnatish**
```bash
pip install -r requirements.txt
```

4. **Bot Token olish**
   - [@BotFather](https://t.me/BotFather) ga o'ting
   - `/newbot` buyrug'ini yuboring
   - Bot nomini va username ni kiriting
   - Olingan token ni saqlang

5. **Konfiguratsiya faylini yaratish**
```bash
# .env faylini yarating
echo "BOT_TOKEN=your_bot_token_here" > .env
```

6. **Botni ishga tushirish**
```bash
python bot.py
```

---

## 🚂 Railway ga deploy qilish

Botni [Railway](https://railway.app) da bepul (yoki pullik) hostingda 24/7 ishlatish mumkin. Quyidagi qadamlarni bajaring.

### 1. Railway hisob ochish

- [railway.app](https://railway.app) ga kiring
- **Login** → GitHub bilan kirish (yoki email)

### 2. Yangi loyiha va deploy

1. **New Project** bosing.
2. **Deploy from GitHub repo** tanlang.
3. GitHubda ShutupBot reponi tanlang (avval fork qilib oling yoki o'z repoingizga push qiling).
4. **Branch**: `main` (yoki asosiy branchingiz).
5. **Root Directory** bo'sh qoldiring (loyiha ildizida).
6. **Deploy** bosilgach Railway avtomatik build qiladi (`requirements.txt` va `railway.toml` ishlatiladi).

### 3. Muhit o'zgaruvchisi (BOT_TOKEN)

1. Ochiq servicingizda **Variables** bo'limiga o'ting.
2. **+ New Variable** bosing.
3. **BOT_TOKEN** nomi, qiymati – [@BotFather](https://t.me/BotFather) dan olgan token (masalan: `7123456789:AAH...`).
4. Saqlang – deploy avtomatik qayta ishga tushadi.

### 4. Start command tekshirish

- **Settings** → **Deploy** bo'limida **Start Command** quyidagicha bo'lishi kerak: `python bot.py`
- Agar `railway.toml` repoda bo'lsa, bu avtomatik o'rnatiladi. Yo'q bo'lsa, qo'lda `python bot.py` kiriting.

### 5. Loglar va holat

- **Deployments** → oxirgi deploy → **View Logs**: bot ishga tushganini va xatolik yo'qligini ko'rasiz.
- Muvaffaqiyatli ishga tushganda logda: `Starting Telegram Moderation Bot...` ko'rinadi.

### 6. Muhim eslatmalar

| Narsa | Tavsif |
|--------|--------|
| **Worker** | Bot web server emas, worker – PORT ochish shart emas. |
| **Token** | `BOT_TOKEN` faqat Railway Variables da saqlang, kodga yozmang. |
| **config.py** | Taqiqlangan so'zlar va jazo muddatlari – repodagi `config.py` dan olinadi. O'zgartirish uchun kodni o'zgartirib push qiling. |
| **Qayta deploy** | Har safar `main` ga push qilsangiz, Railway avtomatik yangi deploy qiladi (GitHub ulangan bo'lsa). |

### Loyihadagi Railway bilan bog'liq fayllar

| Fayl | Vazifasi |
|------|----------|
| `railway.toml` | Start command va restart sozlamalari |
| `Procfile` | `worker: python bot.py` (qo'shimcha platformalar uchun) |
| `runtime.txt` | Python 3.11 versiyasi |
| `.env.example` | Lokal va Railway da qanday o'zgaruvchi kerakligi namuni |

---

## ⚙️ Sozlash

### 🔧 config.py faylini sozlash

```python
# Taqiqlangan so'zlar ro'yxati
FORBIDDEN_WORDS = [
    "so'kinish1", 
    "so'kinish2", 
    "yomonso'z",
    # O'zingizning so'zlaringizni qo'shing
]

# Jazo muddatlari (soniyalarda)
PUNISHMENT_DURATIONS = {
    1: 300,      # 5 daqiqa
    2: 900,      # 15 daqiqa  
    3: 3600,     # 1 soat
    4: 86400     # 1 kun
}
```

### 📝 Xabar shablonlarini o'zgartirish

```python
# Shaxsiy ogohlantirish xabari
BLOCKED_MESSAGE_TEMPLATE = """❌ Siz taqiqlangan so'z ishlatdingiz!

🚫 Sabab: "{word}" so'zi taqiqlangan
⏱ Blok muddati: {duration}
📊 Bugungi kunlik qoida buzishlar soni: {count}/4

Iltimos, guruh qoidalariga rioya qiling."""

# Guruh bildirishnomasi
GROUP_NOTIFICATION_TEMPLATE = """🚫 **Foydalanuvchi bloklandi**

👤 Foydalanuvchi: [{user_name}](tg://user?id={user_id}) `#{user_id}`
🚫 Sabab: "{word}" so'zi ishlatildi
⏱ Blok muddati: {duration}
📊 Bu foydalanuvchining {count}-chi qoida buzishi

_Bu xabar foydalanuvchi blokdan chiqgach o'chadi._"""
```

---

## 📖 Foydalanish

### 🤖 Botni guruhga qo'shish

1. Botni guruhga qo'shing
2. Botga admin huquqlarini bering (xabarlarni o'chirish va foydalanuvchilarni cheklash huquqi)
3. Bot avtomatik ravishda ishlay boshlaydi

### 👥 Admin huquqlari

Bot to'g'ri ishlashi uchun quyidagi huquqlarga ega bo'lishi kerak:
- ✅ Xabarlarni o'chirish
- ✅ Foydalanuvchilarni cheklash
- ✅ Guruh ma'lumotlarini o'qish

### 🔍 Qanday ishlaydi

1. **Xabar tekshirish**: Bot har bir xabarni taqiqlangan so'zlar bilan solishtiradi
2. **Qoida buzish aniqlash**: Agar taqiqlangan so'z topilsa, foydalanuvchi qoida buzish qilgan deb hisoblanadi
3. **Jazo berish**: Progressiv jazo tizimi bo'yicha foydalanuvchi cheklanadi
4. **Xabar yuborish**: Foydalanuvchiga shaxsiy ogohlantirish va guruhga bildirishnoma yuboriladi

---

## 🛠️ Texnik tafsilotlar

### 📚 Ishlatilgan texnologiyalar
- **Python 3.11+**: Asosiy dasturlash tili
- **Aiogram 3.22+**: Telegram Bot API kutubxonasi
- **python-dotenv**: Muhit o'zgaruvchilarini boshqarish

### 🏗️ Loyiha tuzilishi
```
ShutupBot/
├── bot.py              # Asosiy bot kodi
├── config.py           # Konfiguratsiya sozlamalari
├── requirements.txt    # Kerakli kutubxonalar
├── pyproject.toml      # Loyiha konfiguratsiyasi
├── railway.toml        # Railway deploy sozlamalari
├── Procfile            # Worker process (Railway/Heroku)
├── runtime.txt         # Python versiyasi (3.11)
├── .env.example        # Muhit o'zgaruvchilari namuni
└── README.md           # Loyiha hujjati
```

### 🔄 Asosiy komponentlar

#### ModerationBot klassi
- `contains_forbidden_word()`: Taqiqlangan so'zlarni aniqlash
- `restrict_user()`: Foydalanuvchini cheklash
- `send_private_warning()`: Shaxsiy ogohlantirish yuborish
- `send_group_notification()`: Guruh bildirishnomasi

#### Event Handlerlar
- `handle_group_message()`: Guruh xabarlarini qayta ishlash
- `handle_private_message()`: Shaxsiy xabarlarni qayta ishlash

---

## 🎨 Xususiyatlar

### 🎯 Aqlli Algoritm
- **Case-insensitive**: Katta-kichik harflarga e'tibor bermaydi
- **Substring matching**: So'zning bir qismi ham topilsa, qoida buzish deb hisoblanadi
- **Real-time processing**: Xabarlar real vaqtda tekshiriladi

### 🔒 Xavfsizlik
- **Token himoyasi**: Bot token .env faylida saqlanadi
- **Error handling**: Xatoliklarni boshqarish
- **Logging**: Barcha harakatlar log qilinadi

### 📊 Monitoring
- **Violation tracking**: Har bir foydalanuvchining qoida buzishlarini kuzatish
- **Automatic cleanup**: Eski ma'lumotlarni avtomatik tozalash
- **Message management**: Xabarlarni avtomatik o'chirish

---

## 🤝 Hissa qo'shish

Bu loyihaga hissa qo'shish uchun:

1. **Fork** qiling
2. **Feature branch** yarating (`git checkout -b feature/AmazingFeature`)
3. **Commit** qiling (`git commit -m 'Add some AmazingFeature'`)
4. **Push** qiling (`git push origin feature/AmazingFeature`)
5. **Pull Request** yarating

---

## 👨‍💻 Muallif

- GitHub: [@NodirUstoz](https://github.com/NodirUstoz)
- Telegram: [@NodirUstozBot](https://t.me/NodirUstozBot)

---

## 🙏 Minnatdorchilik

- [Aiogram](https://github.com/aiogram/aiogram) - Ajoyib Telegram Bot kutubxonasi
- [Python](https://python.org) - Kuchli dasturlash tili
- [Telegram](https://telegram.org) - Eng yaxshi messenjer

---

## 📞 Aloqa

Savollar yoki takliflar uchun:
- 💬 Telegram: [@NodirUstozBot](https://t.me/NodirUstozBot)
- 🐛 Issues: [GitHub Issues](https://github.com/NodirUstoz/ShutupBot/issues)

---

<div align="center">

**⭐ Agar loyiha sizga foydali bo'lgan bo'lsa yulduzcha qoldiring! ⭐**

</div>
