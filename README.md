<div align="center">
  <img src="https://raw.githubusercontent.com/Riku32/iolite/master/extra/assets/Banner.png"/>
</div>

## iolite
Iolite is a free and open source scripting language inspired by Lua and JavaScript.

## Build
Has been tested on Ubuntu linux
```bash
git clone https://github.com/Riku32/iolite.git
cd iolite
bash setup.sh
cmake CMakeLists.txt
cmake --build cmake-build-debug --target iolite -- -j4
```