# simple-ssh-config
Eh, something I use pretty often. Feel free to use and expand on if needed.

**Usage**
Super simple. But can become more complex when you get into bastion, multiple keys, tunneling etc. Lots of information on the internet available if you need help with that.

**Creating a Sample Config File in Linux**
1. Terminal: ```cd ~/.ssh/ && nano simple-ssh-config``` 
2. Terminal & Save:
```
Host <identifier>
  HostName <host>
  User <user>
  Port <port>
  IdentityFile <~/.ssh/key.key>
```
3. Terminal: ```ssh- F simple-ssh-config <identifier>```
4. Despite everything, it's still you. But at least you've implemented simple-ssh-config.
