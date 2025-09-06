![sm64coopdx Logo](textures/segment2/custom_coopdx_logo.rgba32.png)
sm64coopdx is online multiplayer mod for the Super Mario 64 PC port that synchronizes all entities and every level for multiple players. Fork & official continuation of [sm64ex-coop](https://github.com/djoslin0/sm64ex-coop). 

Feel free to report bugs and contribute, but remember, there must be **no upload of any copyrighted asset**. 
Run `./extract_assets.py --clean && make clean` or `make distclean` to clear ROM assets, however this is unnecessary for contributing because the .gitignore file already excludes ROM assets.

## How to Compile

### Windows:

Download the newest version of the MSYS2 installer from [here](https://github.com/msys2/msys2-installer/releases) and install it.

#### Set up MSYS2.

Run the MINGW64 (`mingw64.exe`) prompt if you wish to build a 64-bit version of the executable, or the MINGW32 (`mingw32.exe`) prompt otherwise.

Enter `pacman -Syuu` in the prompt and hit Enter. Press `Y` when it asks if you want to update packages. If it asks you to close the prompt, do so, then restart it and run the same command again. This updates the packages to their latest versions.

#### Install dependencies.
Enter this command to install packages necessary to build sm64coopdx:

```
pacman -S unzip make git mingw-w64-i686-gcc mingw-w64-x86_64-gcc mingw-w64-i686-glew mingw-w64-x86_64-glew mingw-w64-i686-SDL2 mingw-w64-i686-SDL mingw-w64-x86_64-SDL2 mingw-w64-x86_64-SDL python3
```

### Obtain the source code.
You can either download the ZIP file from github, or clone it with git:
```
git clone https://github.com/GManTheMarioGuy/sm64coopdx.git
cd sm64coopdx
```

#### Copy baserom(s) for asset extraction.
For each version (jp/us/eu) that you want to build an executable for, put an existing ROM at `./baserom.<version>.z64` for asset extraction.

For example, if you want to build the US version, there should be a ROM file called baserom.us.z64 in the sm64coopdx directory (meaning next to the Makefile). The US version is highly recommended.

If during the build process you get messages saying that the ROM has an incorrect hash, there is a possibility that it's a V64 ROM that needs to be byteswapped. To do that, use this [web tool](https://hack64.net/tools/swapper.php).

#### Run `make`. To turn certain features on and off, append any needed build flags to your `make` invocation like so:

#### Useful Flag information:
`-j[2|4|8|16]`: Jobs amount, may speed up compilation.

`TARGET_BITS [32|64]`: Compile 32-bit or 64-bit.

`DISCORD_SDK [0|1]`: Enable or disable Discord Game SDK.

`COOPNET [0|1]`: Enable or disable the CoopNet networking system.

`HEADLESS [0|1]`: Enable or disable headless mode (meant for servers.)

`RENDER_API [GL|GL_LEGACY|D3D11|D3D12|DUMMY]`: Sets the rendering API.

`WINDOW_API [SDL1|SDL2|DXGI|DUMMY]` Sets the window API.

#### Windows
```
make -j
```

## Goal (accomplished)
Create a mod for the PC port where multiple people can play together online.

Unlike previous multiplayer projects, this one synchronizes enemies and events. This allows players interact with the same world at the same time.

## Lua
sm64coopdx is moddable via Lua, similar to Roblox and Garry's Mod's Lua APIs. To get started, click [here](docs/lua/lua.md) to see the Lua documentation.

## Discord
SM64CoopDX DirectX 12 has a Discord server that you can join if you want to download the game, report bugs, etc. To join, click [here](https://discord.gg/a66XPvmrPZ).
