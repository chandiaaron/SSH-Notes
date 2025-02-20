
# SSH - Secure SHell

## What is SSH?
SSH(secure Shell) is network protocol that enables secure communication between computers over a network. 

![SSH IMAGE](/Images/SSHimage1.png) 

## What is an SSH Key Pair?

An SSH key pair consists of a private and public key that work together for secure authenitication. The private key stays on the users machine and should never be shared, whild the public key is placed on the remote server.

## Why is it more secure than HTTPS?

 SSH is designed for secure remote access and direct control over systems, it has stricter security measures than HTTPS.

| Feature           | SSH (Secure Shell)                                  | HTTPS (Hypertext Transfer Protocol Secure) |
|------------------|------------------------------------------------|-------------------------------------------|
| **Purpose**      | Secure remote access, file transfer, and command execution | Secure web browsing and data transfer    |
| **Authentication** | Uses public-key authentication (passwordless login possible) | Uses certificate-based authentication, often with passwords |
| **Encryption Scope** | Encrypts the entire session, including commands and file transfers | Encrypts web traffic (requests and responses) |
| **Two-Way Security** | Mutual authentication between client and server | Primarily authenticates the website, not necessarily the client |
| **Common Use Cases** | Server management, secure shell access, tunneling | Secure website access, online transactions |


## Creating an SSH Key Pair

## Adding the SSH Key pair to GitHub 
