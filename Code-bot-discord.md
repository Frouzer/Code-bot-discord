# Code-bot-discord
Début de code pour programmé son bot



import discord
from discord.ext import commands




bot = commands.Bot(command_prefix = "!", description = "nom du bot")




(des commands pour votre bot
 exemple)




@bot.event
async def on_ready():
	print("Ready !")



@bot.command()
async def coucou(ctx):
	await ctx.send("Coucou !")




@bot.command()
async def serverInfo(ctx):
    server = ctx.guild
    numberOfTextChannels = len(server.text_channels)
    numberOfVoiceChannels = len(server.voice_channels)
    serverDescription = server.description
    numberOfPerson = server.member_count
    serverName = server.name
    message = f"Le serveur **{serverName}** contient *{numberOfPerson}* personnes ! \nLa description du serveur est {serverDescription}. \nCe serveur possède {numberOfTextChannels} salons écrit et {numberOfVoiceChannels} salon vocaux."
    await ctx.send(message)



bot.run("le token de votre bot")
