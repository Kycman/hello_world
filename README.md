# clang
```
sudo apt update && sudo apt upgrade -y
wget --no-proxy -O - https://apt.llvm.org/llvm.sh
chmod +x llvm.sh
sudo ./llvm.sh 22
sudo apt install clang-22 lldb-22 lld-22 libc++-22-dev libc++abi-22-dev
sudo update-alternatives --install /usr/bin/clang clang /usr/bin/clang-22 100 \
--slave /usr/bin/clang++ clang++ /usr/bin/clang++-22
```

# clangd
```
sudo apt install clangd-22
sudo update-alternatives --install /usr/bin/clangd clangd /usr/bin/clangd-22 100
```
2. Configure VS CodeFor the best experience, you should use the official clangd extension for VS Code.Install the Extension: Search for "clangd" in the VS Code Extensions marketplace and install the one by llvm.org.Disable IntelliSense: The default Microsoft C/C++ extension conflicts with clangd. When prompted by the clangd extension, click "Disable IntelliSense".Set the Path: If the extension can't find your server, open your settings (Ctrl + ,), search for clangd.path, and set it to /usr/bin/clangd.
   
# CMake
```
sudo apt-get update
sudo apt-get install ca-certificates gpg wget
wget --no-proxy -O - https://apt.kitware.com/keys/kitware-archive-latest.asc | gpg --dearmor - | sudo tee /usr/share/keyrings/kitware-archive-keyring.gpg >/dev/null

echo "deb [signed-by=/usr/share/keyrings/kitware-archive-keyring.gpg] https://apt.kitware.com/ubuntu/ noble main" | sudo tee /etc/apt/sources.list.d/kitware.list >/dev/null

sudo apt-get update
sudo apt-get install cmake
```

# Ninja
```
sudo apt-get update
sudo apt install ninja-build
```

# ccache
```
sudo apt update
sudo apt install ccache
```

export PATH="/usr/lib/ccache:$PATH"
ccache -M 20G
