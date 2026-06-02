import os
from telegram import Update
from telegram.ext import ApplicationBuilder, CommandHandler, ContextTypes

TOKEN = os.getenv("BOT_TOKEN")

async def start(update: Update, context: ContextTypes.DEFAULT_TYPE):
    await update.message.reply_text(
        "Привет! Напиши:\n\nfroddo 31\nили\nfroddo 26"
    )

async def search(update: Update, context: ContextTypes.DEFAULT_TYPE):
    text = update.message.text.lower()

    if "31" in text:
        await update.message.reply_text(
            "Ищу Froddo barefoot 31 до 15€:\n"
            "https://www.vinted.sk/catalog?search_text=froddo+31+barefoot"
        )

    elif "26" in text:
        await update.message.reply_text(
            "Ищу Froddo barefoot 26 до 15€:\n"
            "https://www.vinted.sk/catalog?search_text=froddo+26+barefoot"
        )

    else:
        await update.message.reply_text("Напиши размер: 31 или 26")

app = ApplicationBuilder().token(TOKEN).build()

app.add_handler(CommandHandler("start", start))

from telegram.ext import MessageHandler, filters
app.add_handler(MessageHandler(filters.TEXT & ~filters.COMMAND, search))

app.run_polling()
