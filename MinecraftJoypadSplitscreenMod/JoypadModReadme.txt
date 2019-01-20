JOYPAD SPLITSCREEN MOD modding

Note: You should have some familiarity with Forge modding.  These instructions won't cover that.

This information is accurate as of Forge 1.8.9 and if history is any guide, some future version will break these instructions :)

Method 1 (the easy method)
This is assuming you want to make some changes to the source and build for yourself.
これは、ソースに何らかの変更を加えて自分で構築したいと想定しています。

Download JOYPAD SPLITSCREEN MOD source from Github as a zip and unzip (i.e. H:\modding\MinecraftJoypadSplitscreenMod-master)
Download latest MDK from FORGE and unzip (i.e. H:\modding\1.8\forge-1.8.9-11.15.1.1722-mdk)
Remove the example src from the MDK (rmdir H:\modding\1.8\forge-1.8.9-11.15.1.1722-mdk\src)
Copy the src from H:\modding\MinecraftJoypadSplitscreenMod-master\src to H:\modding\1.8\forge-1.8.9-11.15.1.1722-mdk\src
Open command window and go to H:\modding\1.8\forge-1.8.9-11.15.1.1722-mdk\
gradlew setupdecompworkspace eclipse
Open eclipse and point workspace to H:\modding\1.8\forge-1.8.9-11.15.1.1722-mdk\eclipse

Method 2 (Community Modder method) 
This is assuming you want to use github for your source control and push any updates you make to GITHub for everyone to enjoy.
これは、あなたがあなたのソース管理にgithubを使い、みんなが楽しむことができるようにGITHubに行った更新をプッシュしたいと仮定しています

Clone the repository (i.e. c:\git\MinecraftJoypadSplitscreenMod\MinecraftJoypadSplitscreenMod)
Download the latest MDK from Forge
Copy these files from the forge MDK to your local repository 
gradlew
gradlew.bat
.gradle\ 
eclipse\

If you are updating Joypad mod to a newer version of Minecraft Forge, then you will need to modify the local repository copy of build.gradle 
before running the next step otherwise you will not get the latest Minecraft source to build against.
Joypad modを新しいバージョンのMinecraft Forgeに更新する場合は、build.gradleのローカルリポジトリコピーを変更する必要があります。
そうでなければ、次のステップを実行する前に、最新のMinecraftソースを構築することはできません。

The easiest way to do this is to open the build.gradle from the Forge MDK you downloaded.  Copy most of this into the build.gradle of the 
Joypad repository version but keep this info:
これを行う最も簡単な方法は、ダウンロードしたForge MDKからbuild.gradleを開くことです。このほとんどを、のbuild.gradleにコピーしてください。
Joypadリポジトリのバージョンですが、この情報を保管してください。

version = "1.8.9-11.15.1.1722" 
group = "com.shiny.joypadmod"
archivesBaseName = "JoypadMod"

*modify the version info to something that reflects the newer version of Forge you are using
Also, you will need to keep this dependency:
compile 'org.lwjgl.lwjgl:lwjgl:2.+' 

Open command window and go to c:\git\MinecraftJoypadSplitscreenMod\MinecraftJoypadSplitscreenMod
gradlew setupdecompworkspace eclipse
Open eclipse and point workspace to c:\git\MinecraftJoypadSplitscreenMod\MinecraftJoypadSplitscreenMod\eclipse

When you've tested your changes request to get the changes into MinecraftJoypadSplitscreenMod!

Notes:
The name of the project will likely be MDKExample but the source will just be the joypad mod.   
To get eclipse to show the debug buttons, open one of the joypad mod source files.
If you are using a later version of Forge there may be some errors in the JOYPAD mod source.  Find those errors and fix them!
