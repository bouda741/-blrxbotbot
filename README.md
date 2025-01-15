
البوت فري فاير from pyrogram import Client, filters

# إعداد البوت
app = Client(
    "FakeFriendBot",
    bot_token="ضع هنا توكن البوت الخاص بك",
    api_id=1234567,  # استبدل بـ API ID الخاص بك
    api_hash="ضع هنا API HASH الخاص بك"
)

# أمر صديق وهمي
@app.on_message(filters.command("BZ"))
def fake_friend(client, message):
    message.reply_text("تم إنشاء صديق وهمي جديد 🎭.")

# أمر التحكم في السكواد
@app.on_message(filters.command("CP"))
def control_squad(client, message):
    message.reply_text("تم تفعيل التحكم في السكواد 🎮.")

# تجهيز 5 سكوادات
@app.on_message(filters.command("5سكواد"))
def squad_5(client, message):
    message.reply_text("تم تجهيز 5 سكوادات! 🚀.")

# تجهيز 6 سكوادات
@app.on_message(filters.command("6سكواد"))
def squad_6(client, message):
    message.reply_text("تم تجهيز 6 سكوادات! 🚀.")

# وضع المقبرة 24 ساعة
@app.on_message(filters.command("مقبرا"))
def graveyard_24h(client, message):
    message.reply_text("تم تفعيل وضع المقبرة لمدة 24 ساعة 💀.")

# فك وضع المقبرة
@app.on_message(filters.command("فك"))
def unlock_graveyard(client, message):
    message.reply_text("تم فك وضع المقبرة بنجاح ✅.")

# دخول سكواد مخفي
@app.on_message(filters.command("!id"))
def hidden_squad(client, message):
    message.reply_text("تم دخول السكواد في وضع المخفي 🕶️.")

# دخول سكواد عادي
@app.on_message(filters.command("*id"))
def normal_squad(client, message):
    message.reply_text("تم دخول السكواد في الوضع العادي. 🎮.")

# بدء تشغيل البوت
print("البوت يعمل الآن...")
app.run()
pip install pyrogram tgcrypto
python fake_friend_bot.py
pip install pyrogram tgcrypto
/start
/newbot
cd C:\Users\YourName\Documents
python fake_friend_bot.py
البوت يعمل الآن...
