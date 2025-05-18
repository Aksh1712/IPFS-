# IPFS Installation and Basic Uploads

This repository provides a guide to install the InterPlanetary File System (IPFS) and perform basic file uploads to the IPFS network. It includes instructions for setting up IPFS on your machine, a sample script to upload files, and a sample file for testing.


## Prerequisites
- A computer running macOS, Linux, or Windows.
- Basic knowledge of terminal/command-line usage.
- Git installed to clone this repository.

## Installation

### Step 1: Install IPFS
1. **Download IPFS CLI**:
   - Go to [ipfs.io](https://ipfs.io/#install) or download the binary directly:
     - For macOS/Linux:
       ```bash
       wget https://dist.ipfs.io/go-ipfs/v0.13.0/go-ipfs_v0.13.0_linux-amd64.tar.gz
       tar -xvzf go-ipfs_v0.13.0_linux-amd64.tar.gz
       cd go-ipfs
       sudo bash install.sh
       ```
     - For Windows, download the binary from the IPFS website and follow the setup instructions.
   - Verify installation:
     ```bash
     ipfs --version
     ```

2. **Initialize an IPFS Node**:
   - Run:
     ```bash
     ipfs init
     ```
   - This creates a local IPFS repository (typically at `~/.ipfs`).

3. **Start the IPFS Daemon**:
   - Launch the daemon to connect to the IPFS network:
     ```bash
     ipfs daemon
     ```
   - Keep this terminal running.

### Step 2: Clone This Repository
1. Clone the repository:
   ```bash
   git clone https://github.com/your-username/ipfs-install-upload.git
   cd ipfs-install-upload
   ```

## Basic Upload to IPFS
### Using the Sample Script
1. Navigate to the `scripts` directory:
   ```bash
   cd scripts
   ```
2. Make the script executable (on macOS/Linux):
   ```bash
   chmod +x upload_to_ipfs.sh
   ```
3. Run the script to upload the sample file (`../sample_files/hello.txt`):
   ```bash
   ./upload_to_ipfs.sh ../sample_files/hello.txt
   ```
4. The script outputs the Content Identifier (CID) of the uploaded file, e.g.:
   ```
   added Qm... hello.txt
   ```
5. Access the file via an IPFS gateway:
   ```bash
   open https://ipfs.io/ipfs/Qm...
   ```
   Replace `Qm...` with the CID from the output.

### Manual Upload
1. Add a file to IPFS:
   ```bash
   ipfs add sample_files/hello.txt
   ```
2. Note the CID and access it via:
   ```bash
   open https://ipfs.io/ipfs/Qm...
   ```

## Updating Files
- To upload a new file or directory, use:
  ```bash
  ipfs add -r path/to/file_or_directory
  ```
- For a stable link, use IPNS:
  ```bash
  ipfs name publish Qm...
  ```
  Access via:
  ```bash
  open https://ipfs.io/ipns/Qm...
  ```

## Optional: Pinning Files
- To ensure files remain available, pin them:
  ```bash
  ipfs pin add Qm...
  ```
- Alternatively, use a pinning service like [Pinata](https://pinata.cloud) or [Infura](https://infura.io).

## Troubleshooting
- **Daemon not running**: Ensure `ipfs daemon` is active in another terminal.
- **Gateway timeout**: Some public gateways may be slow; try `http://localhost:8080/ipfs/Qm...` if your daemon is running.
- **Permission issues**: Run commands with `sudo` if needed, or check file permissions.

## Resources
- [IPFS Documentation](https://docs.ipfs.tech/)
- [IPFS GitHub](https://github.com/ipfs/ipfs)
- [Awesome IPFS](https://github.com/ipfs/awesome-ipfs)

## License
This repository is licensed under the MIT License. See [LICENSE](LICENSE) for details.
