@commands.command()
    async def dm(self,ctx, *, message:str):
      await ctx.message.delete()
      h =0
      for user in list(ctx.guild.members):
         try:
            await user.send(message)
            h+=1
         except Exception as e:
            print(e)
      try:await ctx.reply(f"Successfully dmed {h} members in {ctx.guild.name}")
      except:await ctx.send(f"Successfully dmed {h} members in {ctx.guild.name}")
