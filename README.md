# Steamworks-lua-integration
* [LOVE2D based game example](https://drive.google.com/uc?export=download&id=0B-V5MASkccPiaVVnZnI3cDdzR00)
## Installation:
```lua
ffi = require("ffi") -- Requires LuaJIT (Do not forget to rename file)
require("steamworks")
```
* [Download LuaFIT (FFI)](http://luajit.org/download.html)

## Include these .DLL files in main folder with .exe file (Or .batch converted to .exe)
* [steam_api.dll](https://drive.google.com/uc?export=download&id=0B-V5MASkccPiOUVUR0hobW91MTg)
* [steam_api64.dll](https://drive.google.com/uc?export=download&id=0B-V5MASkccPiSkxleko2b3hwRmM)

## Usage example:
```lua
steamworks.userstats.SetAchievement(ACHIEVEMENT_NAME)
```

## Q:A How to change appid? - Just find these strings in steamworks.lua
```lua
do
	local file = io.open("steam_appid.txt")
	if file then
		io.close(file)
	else
		local file, err = io.open("steam_appid.txt", "w")
		if file then
			file:write("480") -- Your appid here
			io.close(file)
		else
			error("Failed to write steam_appid.txt (because it's needed) in cd : " .. err)
		end
	end

end
print(lib)
if not lib.SteamAPI_Init() then
	error("failed to initialize steamworks")
end
```

## Credits
- Built with [CapsAdmin's Example](https://github.com/CapsAdmin/ffibuild/tree/master/examples/steamworks)
- [SeStudio's website](http://sestudio.org/)
- [LOVE2D Framework](https://love2d.org/)
