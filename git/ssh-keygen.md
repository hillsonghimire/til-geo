## SSH github setup in Windows - SSH-KEYGEN

For `Windows`
```cmd
ssh-keygen -o -t rsa -C "mail@gmail.com"
```
Saving it to default  `C:\Users\UserName/.ssh/id_rsa`
## Check the id_rsa.pub file

```cmd
C:\Users\UserName\.ssh\> dir
LastWriteTime      Name
-------------      ----
1/1/2022           id_rsa
1/1/2022           id_rsa.pub
```
Copy content from `id_rsa.pub`, the content can be viewed using `type` command equivalent to `cat` in linux.
```cmd
C:\Users\UserName\.ssh>type id_rsa.pub

ssh-rsa
XXXXXXXXXXXXXXXXX
XXXXXXXXXXXXXXXXX
XXXXXXXXXXXXXXXXX
XXXXXXXXXXXXXXXXX= mail@gmail.com
```

Copy this response and paste it in [github SSH configuration setting page](https://github.com/settings/keys)