Installation

Step 1: Install IPFS





Download IPFS CLI:





Go to ipfs.io or download the binary directly:





For macOS/Linux:

wget https://dist.ipfs.io/go-ipfs/v0.13.0/go-ipfs_v0.13.0_linux-amd64.tar.gz
tar -xvzf go-ipfs_v0.13.0_linux-amd64.tar.gz
cd go-ipfs
sudo bash install.sh



For Windows, download the binary from the IPFS website and follow the setup instructions.



Verify installation:

ipfs --version



Initialize an IPFS Node:





Run:

ipfs init



This creates a local IPFS repository (typically at ~/.ipfs).



Start the IPFS Daemon:





Launch the daemon to connect to the IPFS network:

ipfs daemon



Keep this terminal running.

Step 2: Clone This Repository





Clone the repository:

git clone https://github.com/your-username/ipfs-install-upload.git
cd ipfs-install-upload

Basic Upload to IPFS

Using the Sample Script





Navigate to the scripts directory:

cd scripts



Make the script executable (on macOS/Linux):

chmod +x upload_to_ipfs.sh



Run the script to upload the sample file (../sample_files/hello.txt):

./upload_to_ipfs.sh ../sample_files/hello.txt



The script outputs the Content Identifier (CID) of the uploaded file, e.g.:

added Qm... hello.txt



Access the file via an IPFS gateway:

open https://ipfs.io/ipfs/Qm...

Replace Qm... with the CID from the output.

Manual Upload





Add a file to IPFS:

ipfs add sample_files/hello.txt



Note the CID and access it via:

open https://ipfs.io/ipfs/Qm...

Updating Files





To upload a new file or directory, use:

ipfs add -r path/to/file_or_directory



For a stable link, use IPNS:

ipfs name publish Qm...

Access via:

open https://ipfs.io/ipns/Qm...

Optional: Pinning Files





To ensure files remain available, pin them:

ipfs pin add Qm...



Alternatively, use a pinning service like Pinata or Infura.

Troubleshooting





Daemon not running: Ensure ipfs daemon is active in another terminal.



Gateway timeout: Some public gateways may be slow; try http://localhost:8080/ipfs/Qm... if your daemon is running.



Permission issues: Run commands with sudo if needed, or check file permissions.

Resources





IPFS Documentation



IPFS GitHub



Awesome IPFS

License

This repository is licensed under the MIT License. See LICENSE for details.
