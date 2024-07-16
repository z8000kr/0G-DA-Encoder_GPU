# 0G-DA-Encoder_GPU

### nvidia driver install
```bash
sudo apt install nvidia-utils-550
```
### nvidia cuda install
```bash
sudo apt install nvidia-cuda-toolkit
```
### nvidia version
```bash
nvidia-smi && nvcc --version
```
### git install
```bash
git clone https://github.com/0glabs/0g-da-encoder.git
```
### amt download
```bash
cd 0g-da-encoder/dev_support
./download_params.sh
sudo cp -R /root/0g-da-encoder/dev_support/params /root/0g-da-encoder
```
### lib install
```bash
cd
cd 0g-da-encoder
```
```bash
sudo apt-get install protobuf-compiler
```
### encoder build
```bash
cargo run -r -p server --features grpc/parallel -- --config /root/0g-da-encoder/run/config.toml
```
### da-node cargo config.toml setup
#zg-encoder = { git = "https://github.com/0glabs/0g-da-encoder.git", rev = "6d5bac1", features = ["paral>
zg-encoder = { path = "../0g-da-encoder/crates/encoder", features = ["cuda"]}
task_executor = { git = "https://github.com/0glabs/0g-storage-node.git", rev = "ef82f643932ad0a2ec28acce>

