
from telegram import Update
from telegram.ext import Application, CommandHandler, ContextTypes
import os

TOKEN = os.getenv("BOT_TOKEN")

async def start(update: Update, context: ContextTypes.DEFAULT_TYPE):
    await update.message.reply_text(
        "👋 Tongasoa eto amin'ny MC Trade News Bot!\n\n"
        "/news - Vaovao Forex\n"
        "/sessions - Session Trading\n"
        "/gold - Analyse XAUUSD"
    )

app = Application.builder().token(TOKEN).build()

app.add_handler(CommandHandler("start", start))

app.run_polling()
