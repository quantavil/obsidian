This guide focuses on teaching you how to use Xavy's Torrent to GDrive script in short without any confusions.  
Using the script, you can download torrents straight into your google drive, without having to use your own bandwidth.  
Please read the FAQ at the bottom too.

Here's the link to the script - {Collab Link](https://colab.research.google.com/drive/1DZaeYPp9BCEwxqHaU8fedjYqjO90s8sR?usp=sharing)

There are 4 steps to using the colab, we'll call them 0, 1, 2 and 3.

![Steps](https://cdn.discordapp.com/attachments/835064599026991128/866632029549232138/unknown.png "Steps")

**First, you have to login to your google account that has the google drive folder you want to torrent to.**  
**So next, click the connect option ( Step 0 ), this will connect you to google servers. Wait for a few seconds, it should then show this -**

![RuntimeConnected](https://cdn.discordapp.com/attachments/835064599026991128/866374743326195732/unknown.png "RuntimeConnected")

**Next, You need to run the first cell ( The play button on step 1 ). If it warns you saying the script is from GitHub, just click " Run Anyway. " It will give you a link, click and chose the account that you logged in earlier.  
It will give you a code, you can copy it by clicking the clipboard sign right next to the code. Paste it into the box that says " Enter Authorization Code " and hit enter.**

![Authorization](https://cdn.discordapp.com/attachments/835064599026991128/866740009418620958/unknown.png "Authorization")

**Wait for a bit until it says " Done. " This means you're ready to move on to the next step, and it's pretty much easy from this point on.**

**By default, the torrents are set to go to " My Drive. " If you wish to change this ( you probably will due to storage issues ) click on the folder icon in the bar on the left.**  
![EditSaveDirectory](https://cdn.discordapp.com/attachments/835064599026991128/866743069365895188/unknown.png "EditSaveDirectory")

**Find whatever folder you wish to chose, right click and select " Copy Path. "**  
![EditSaveDirectory2](https://cdn.discordapp.com/attachments/835064599026991128/866747984259842048/unknown.png "EditSaveDirectory2")

**Next, replace your copied folder path with the one already there, so it'll look like this -**

![EditSaveDirectory3](https://cdn.discordapp.com/attachments/835064599026991128/866939660004360192/unknown.png "EditSaveDirectory3")

**Then run the " Start qBitTorrent " cell ( press the play button on step 2 ). It'll give you a link, open it and you should see a web version of qBitTorrent.

**From this point on, it's basically as simple as using any torrent client. Wait for a while depending on how big the file is, then close colab or else it won't get written to your GDrive. Best to check where it's there.**

**By default, the free version of colab will kick you out after 12 hours, run the 3rd cell to bypass that problem.**

# FAQ

Q. Is there a limit to the size of torrent I can use with colab?  
A. Yes. Since the free version of Google Colab only gives you 107GB of RAM, it's best not to go over a 50 gig torrent or multiple torrents that add up to 50 gigs because if the RAM fills up the script will close itself and your progress will be lost.

Q. When I try opening the qBit link, I get an error.  
A. If you're on Firefox, disable tracking protection, try disabling some extensions that could mess with trackers.

Q. Do I need to use a VPN?  
A. No, since everything is done through Google's collaboratory servers, you don't need a VPN.

Think there's something more that can be added to this? DM Sinister_Shadow#9634 on discord.