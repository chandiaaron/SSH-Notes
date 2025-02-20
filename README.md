
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


## Creating an SSH Key Pair(for the first time)

- First you need to open GitBash and make a directroy on your computer called " .ssh ". we can check if this worked by running the list command, you should see your file.
```
mkdir .ssh
ls -a
```

- we need to make sure we are working that directory. 
```
cd .ssh
```


- next we need to generate our keys.
```
ssh-keygen -t rsa -b 4096 -C "Your Email" 
```

you will be prompted to create a file name, for example: git-hub-your name-k
you can then press enter twice and you should see some output such as the RSA 4096.

- We can then check our directory and you should see both keys present 


## Adding the SSH Key pair to GitHub 

From the previous section I will now show you how to use those keys to sync with github.

- Firstly we want to open the contents of the public key, if you are unsure its the file ending in .pub 

you want to copy the contents of that file, make sure you dont inlcude any white space as the following step wont work. 

- Head over to GitHub and click setting and then select SSH and GPG keys and click new SSH key 
- Give your new SSH key a name, it doesnt have to match the previous name given for your key. 
- Next copy and paste the contents of the public key and add SSH key 

- Open your GitBash and we are going to start the SSH authentication agent. This will allow you to add the key once and use them for multiple SSH connections. 

```
eval `ssh-agent -s`
```
- Then we can add the SSH private key to the SSH agent

```
ssh-add github-Your name-key
```

- we can then etablish the connection with github 

```
ssh -T git@github.com
```
-T disables terminal allocation

you will be promted, just simply type yes and click enter 

```
Hi <GitHub-username>! You've successfully authenticated, but GitHub does not provide shell access.

```

