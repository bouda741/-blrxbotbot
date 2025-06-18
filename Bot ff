import telebot import requests import threading import time

=== CONFIG ===

BOT_TOKEN = "6995871108:AAFqlZ0_SERlbFpwogPTiOfoKJ0FZn0Cg4w" OWNER_ID = 7660697431  # Your Telegram ID FF_TOKEN = "598881995E257B6C65147F6568634932B843BC5A3D470B8A37E8B8DF0891549E" FF_UID = "3970648044"

bot = telebot.TeleBot(BOT_TOKEN)

=== Fake API Handler (simulate action) ===

def send_ff_action(action, target_uid=None): print(f"[ACTION] {action} => {target_uid or FF_UID}") return {"status": "success", "action": action, "target": target_uid}

def get_friend_list(): return ["12345678", "87654321"]

def send_message(uid, msg): print(f"[SEND MESSAGE] To {uid}: {msg}")

=== Auto Message Broadcast ===

def auto_reply_to_friends(): msg = '''[11EAFD][b][c] °°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°° إقبل طلب بسرعة!!! °°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°°° [FFB300][b][c]BOT MADE BY CODEX TEAM

🤖 أوامر: /like [UID] /invite [UID] /status''' while True: friend_uids = get_friend_list() for uid in friend_uids: send_message(uid, msg) time.sleep(600)

threading.Thread(target=auto_reply_to_friends, daemon=True).start()

=== Command Handlers ===

@bot.message_handler(commands=['start', 'help']) def send_help(message): if message.from_user.id != OWNER_ID: return help_text = ( "🤖 أوامر البوت الصديق:\n" "/add [UID] - إرسال طلب صداقة\n" "/invite [UID] - دعوة حساب\n" "/like [UID] - إرسال لايك\n" "/status - حالة الحساب\n" "/5 - فتح سكواد 5 لاعبين\n" "/help - عرض الأوامر" ) bot.reply_to(message, help_text)

@bot.message_handler(commands=['add']) def add_cmd(message): if message.from_user.id != OWNER_ID: return try: uid = message.text.split()[1] res = send_ff_action("add_friend", uid) bot.reply_to(message, f"🤝 تم إرسال طلب صداقة إلى UID: {uid}") except: bot.reply_to(message, "❌ يرجى كتابة UID بعد الأمر مثل: /add 1234567890")

@bot.message_handler(commands=['invite']) def invite_cmd(message): if message.from_user.id != OWNER_ID: return try: uid = message.text.split()[1] res = send_ff_action("invite", uid) bot.reply_to(message, f"✅ تمت دعوة UID: {uid}") except: bot.reply_to(message, "❌ يرجى كتابة UID بعد الأمر مثل: /invite 1234567890")

@bot.message_handler(commands=['like']) def like_cmd(message): if message.from_user.id != OWNER_ID: return try: uid = message.text.split()[1] res = send_ff_action("like", uid) bot.reply_to(message, f"❤️ لايك مرسل إلى UID: {uid}") except: bot.reply_to(message, "❌ يرجى كتابة UID بعد الأمر مثل: /like 1234567890")

@bot.message_handler(commands=['status']) def status_cmd(message): if message.from_user.id != OWNER_ID: return bot.reply_to(message, f"📡 حساب البوت شغال ✅\nUID: {FF_UID}")

@bot.message_handler(commands=['5']) def squad_5_cmd(message): if message.from_user.id != OWNER_ID: return squad = ["12345678", "23456789", "34567890", "45678901"] for uid in squad: send_ff_action("invite", uid) bot.reply_to(message, "✅ تم فتح سكواد 5، الدعوات أُرسلت ✅")

=== Run bot ===

bot.polling()

