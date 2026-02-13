# =============================================================================
# PROCFILE — Protsesslar ro'yxati
# =============================================================================
# Bu fayl platformaga (Railway, Heroku va boshqalar) qanday protsesslarni
# ishga tushirish kerakligini aytadi. Har bir qator format: "tip: buyruq"
#
# "web" — brauzer ochadigan server (Flask, FastAPI va h.k.). PORT ochadi.
# "worker" — orqa fonda ishlaydigan dastur; port ochish shart emas.
#
# ShutupBot Telegram polling rejimida ishlaydi (web server emas), shuning uchun
# "worker" tipi ishlatiladi. Platforma shu buyruqni ishga tushiradi va bot
# 24/7 Telegram API dan yangilanishlarni kutib turadi.
# =============================================================================

worker: python bot.py
