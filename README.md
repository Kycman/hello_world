sudo apt update && sudo apt upgrade -y
wget --no-proxy -O - https://apt.llvm.org/llvm.sh
chmod +x llvm.sh
sudo ./llvm.sh 22
sudo apt install clang-22 lldb-22 lld-22 libc++-22-dev libc++abi-22-dev
sudo update-alternatives --install /usr/bin/clang clang /usr/bin/clang-22 100 \
--slave /usr/bin/clang++ clang++ /usr/bin/clang++-22
