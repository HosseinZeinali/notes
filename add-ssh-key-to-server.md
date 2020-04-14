# Add ssh key to server
1-generate RSA key in the local
```
ssh-keygen -t rsa (-b 4096 -C "your_email@domain.com")
```
2-append the generated public key to authorized_keys in the server
or use this command:
```
ssh-copy-id server_user@server_ip
```
3-go to /etc/ssh/ directory. then open `sshd_config` file
and edit it:
* Set `AuthorizedKeysFile`
* Change `PubkeyAuthentication` to yes
* Change `RSAAuthentication` to yes
* Change `ChallengeResponseAuthentication` to no
* Change `PasswordAuthentication` to no
4- Afterwards run this command in the server order to restart ssh service
```
sudo systemctl reload ssh
```
---
For debugging you can use these commands
```bash
ssh -v ( or -vv) username@host's
```