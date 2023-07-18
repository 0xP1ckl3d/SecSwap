# SecSwap

SecSwap is a script designed to facilitate file exchanges between target and attack machines during penetration testing engagements. It leverages the HTTP client-server model and provides built-in simple authentication.

## Features

- HTTP Client-Server Model: SecSwap uses the HTTP protocol to transfer files, allowing it to work across a variety of networking environments.

- Built-in Simple Authentication: For added security, SecSwap supports an optional password authentication. This helps ensure that only authorized individuals can upload or download files from the server. Please note that passwords are merely encoded in base64 and the communication does not use encryption.

- File Listing: The script provides the functionality to list all files and directories on the host. This makes it easier to find and download the files you're interested in.

- File Upload and Download: The script supports simple, user-friendly file upload and download functionality between client and server.

## Usage

To start the server:
```bash
./secswap server -a
```

To use the client:
```bash
./secswap client -s [server address] -p [port number] -ls [optional directory] -a
```

## Installation

On Debian based systems, you can make the script executable and move it into your PATH. From the directory containing the script:
```bash
chmod +x secswap
sudo mv secswap /usr/local/bin
```

This will allow you to run SecSwap from anywhere.

Additionally, you can pull a copy of the script from the SecSwap server using curl, wget, powershell, etc from path http://[server address]/secswap even when secswap is not hosted in your servers directory.

## Examples
```bash
To list the files on the server:
./secswap client -s 192.168.1.3 -ls -a
```

To upload a file to the server:
```bash
./secswap client -s 192.168.1.3 -u test2 -a
```

To download a file from the server:
```bash
./secswap client -s 192.168.1.3 -d test1 -a
```

## Important Note

This script is intended for testing and development purposes only. The server should only be active for a short time while transferring files, and passwords should be unique for each usage. SecSwap does not use encrypted communication and only encodes passwords in base64. Use it responsibly in your penetration testing engagements.
