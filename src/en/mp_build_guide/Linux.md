# Phira-mp Linux Guide

### Using pre-built binaries

1. Get the pre-built binary from [Phira download site](https://phira.dmocken.top/mulity) (or another source).
2. Download with `wget [url]`. If the file is a zip, unzip it and `cd` to the directory containing the binary.
3. Run with `./[filename]` or `./[filename] --port [port]`.

### Building the official Rust version

1. Install Rust if needed: follow [https://www.rust-lang.org/tools/install](https://www.rust-lang.org/tools/install).
   - Ubuntu/Debian: install curl first: `sudo apt install curl`
   - Fedora/CentOS: `sudo yum install curl`
   - Then: `curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh`

2. Clone the repo:
   - Install git:

   | Distro | Command |
   | :--- | :--- |
   | **Debian / Ubuntu** | `sudo apt update && sudo apt install git` |
   | **RHEL / CentOS 7 and below** | `sudo yum install git` |
   | **RHEL / CentOS 8+ / Fedora** | `sudo dnf install git` |
   | **Arch Linux** | `sudo pacman -S git` |
   | **openSUSE** | `sudo zypper install git` |

   Then: `git clone https://github.com/TeamFlos/phira-mp.git`

3. Build:
   ```shell
   cd phira-mp
   cargo build --release -p phira-mp-server
   ```

#### Running the server

- Run: `RUST_LOG=info target/release/phira-mp-server`
- Or with a port: `RUST_LOG=info target/release/phira-mp-server --port 8080`

### Docker

1. Create a Dockerfile (see source for full content). Use Ubuntu 22.04, install curl/git/build-essential/openssl, install Rust, clone phira-mp, build with cargo. ENTRYPOINT runs phira-mp-server with your preferred port.

2. Build: `docker build --tag phira-mp .`
3. Run: `docker run -it --name phira-mp -p <port>:<port> --restart=unless-stopped phira-mp`

#### Troubleshooting

- For OpenSSL issues, install libssl-dev (Ubuntu/Debian) or openssl-devel (Fedora/CentOS). You can set OPENSSL_DIR if needed.
- For pkg-config: `sudo apt install pkg-config libssl-dev` (Debian/Ubuntu) or `sudo dnf install pkg-config openssl-devel` (Fedora/CentOS).

#### Monitoring

Check process and port:
```shell
ps -aux | grep phira-mp-server
netstat -tuln | grep 12346
```
