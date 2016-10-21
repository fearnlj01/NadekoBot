________________________________________________________________________________
*Thanks to @Flatbread and Mirai for making this guide*
________________________________________________________________________________

### Setting Up NadekoBot on Windows
#### Prerequisites 
- 1) [.NET Core SDK][.NET Core SDK]
- 2) [Git][Git]
- 3) [FFMPEG][FFMPEG] 
- 4) Google Account
- 5) Soundcloud Account (if you want soundcloud support)
- 6) [7zip][7zip] (or whatever you are using, WinRar)
- 7) [Notepad++][Notepad++]
- 8) Windows 8 or newer

####Guide 
- Make sure you have installed both [Git][Git] and the [.NET Core SDK][.NET Core SDK].
- Create a folder somewhere and name it `Nadeko`.
- Head to the [Windows Installer releases page][WinInstaller] and download the latest source code zip.
- Extract the contents of the zip you just downloaded to the `Nadeko` folder that we created earlier.
- You will see a few files, most importantly, `NadekoInstaller.bat ` after extraction (You may not see the `.bat` part of the filename).
- Run/Launch/Open `NadekoInstaller.bat ` and you will see it running in the command prompt.
- Wait a while for the file to finish installing, it'll say when it's done in the command prompt.
- You should now have a new folder named `NadekoBot` inside the `Nadeko` folder we previously created.
- You can safely delete the `NadekoInstall_Temp` folder if you so choose.

####Creating DiscordBot application
- Go to [the Discord developer application page][DiscordApp].
- Log in with your Discord account.
- On the left side, press `New Application`.
- Fill out the `App Name` (your bot's name, in this case), put the image you want, and add an app description(optional).
- Create the application.
- Click on `Create a Bot User` and confirm that you do want to add a bot to this app.
- Keep this window open for now.

####Setting up Credentials.json file
- In our `NadekoBot` folder you should see a `src` folder, then *another* `NadekoBot` folder, in this final folder, you should see a `.json` file named `credentials_example.json`. (Note: If you do not see a **.json** after `credentials_example.json `, do not add the `**.json**`. You most likely have `"Hide file extensions"` enabled.)
- Rename `credentials_example.json` to `credentials.json`.
- Open the file with [Notepad++][Notepad++].
- In there you will see fields such as `Token`, `ClientId`, `BotId` and `OwnerIDs`.
- In your [applications page][DiscordApp] (the window you were asked to keep open earlier), under the `Bot User` section, you will see `Token:click to reveal`, click to reveal the token.
- Copy your bot's token, and on the `"Token"` line of your `credentials.json`, paste your bot token between the quotation marks.
- Copy the `Client ID` on the page and replace the `12312123` part of the `ClientId` line with it.
- Again, copy the same `Client ID` and replace the `null` part of the `BotId` line with it.
- Save your `credentials.json` but keep it open. We need to add your `User ID` as one of the `OwnerIds` shortly.

####Inviting your bot to your server 
- [Invite Guide][Invite Guide]
- Create a new server in Discord.
- Copy your `Client ID` from your [applications page][DiscordApp].
- Replace the `12345678` in this link `https://discordapp.com/oauth2/authorize?client_id=12345678&scope=bot&permissions=66186303` with your `Client ID`.
- The link should now look like this: `https://discordapp.com/oauth2/authorize?client_id=**YOUR_CLENT_ID**&scope=bot&permissions=66186303`.
- Go to the newly created link and pick the server we created, and click `Authorize`.
- The bot should have been added to your new server.

####Starting the bot
- Go to the folder which you extracted the zip to earlier, and run the `NadekoRun.bat` file
- Your bot should now be online in the server we added her to.
- Note: Your bot will be offline in case you close the `NadekoBot` command prompt window.

####Setting up OwnerIds
- In the server where your bot is, in a text channel, type `.uid`
- Your `User ID` should show, copy it.
- Close `NadekoBot`
- Replace the `0` on the `OwnerIds` section with your user ID shown earlier.
- Run `NadekoRun.bat` again.
- If done correctly, you are now the bot owner.
- You can add multiple owner IDs by seperating them with a comma within the square brackets.

________________________________________________________________________________

#### Setting Up NadekoBot For Music
##### Prerequisites
- 1) [FFMPEG][FFMPEG] installed.
- 2) Setting up API keys.

- Follow these steps on how to setup Google API keys:
    - Go to [Google Console][Google Console] and log in.
    - Create a new project (name does not matter). Once the project is created, go into "Enable and manage APIs."
    - Under the "Other Popular APIs" section, enable `URL Shortener API` and `Custom Search Api`. Under the `YouTube APIs` section, enable `YouTube Data API`.
    - On the left tab, access `Credentials`. Click `Create Credentials` button. Click on `API Key`. A new window will appear with your `Google API key`. 
    - Copy the key.
    - Open up `credentials.json`. 
    - For `"GoogleAPIKey"`, replace `null` with the new key we copied and put quotation marks before and after the API key, like how the `Token` and `ClientId` should be set up.
- Follow these steps on how to setup Soundcloud API key:
    - Go to [Soundcloud][Soundcloud]. 
    - Enter a name for the app and create it. 
    - You will need to fill out an application form to request access to the Soundcloud API.
    - All requests for an API key must go through the review process, where applications will be reviewed on a case by case basis, in line with Soundcloud API Terms of Use. If your application is successful, you will receive an API key. 
- **Restart your computer**.

####Manual `ffmpeg` setup 
**Do this step in case you were not able to install `ffmpeg` with the installer.**

- Create a folder named `ffmpeg` in your main Windows directory. We will use **C:\ffmpeg** (for our guide)
- Download FFMPEG through the link https://ffmpeg.zeranoe.com/builds/ (download static build)
- Extract it using `7zip` and place the folder `ffmpeg-xxxxx-git-xxxxx-xxxx-static` inside **C:\ffmpeg**
- Before proceeding, check out this gif to set up `ffmpeg` PATH correctly [http://i.imgur.com/aR5l1Hn.gif](http://i.imgur.com/aR5l1Hn.gif) *(thanks to PooPeePants#7135)*
- Go to My Computer, right click and select Properties. On the left tab, select Advanced System Settings. Under the Advanced tab, select Environmental Variables near the bottom. One of the variables should be called "Path". Add a semi-colon (;) to the end followed by your FFMPEG's **bin** install location (**for example C:\ffmpeg\ffmpeg-xxxxx-git-xxxxx-xxxx-static\bin**). Save and close.
- Setup your API keys as explained above.
- Restart your computer.

[.NET Core SDK]: https://go.microsoft.com/fwlink/?LinkID=827524
[Git]: https://git-scm.com/download/win
[WinInstaller]: https://github.com/fearnlj01/NadekoBotInstallerWin/releases
[FFMPEG]: https://github.com/Soundofdarkness/FFMPEG-Inst/releases
[7zip]: http://www.7-zip.org/download.html
[DiscordApp]: https://discordapp.com/developers/applications/me
[Notepad++]: https://notepad-plus-plus.org/
[Invite Guide]: http://discord.kongslien.net/guide.html
[Google Console]: https://console.developers.google.com
[Soundcloud]: https://soundcloud.com/you/apps/new
