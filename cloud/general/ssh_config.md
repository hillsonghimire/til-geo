## Setting up configuration like `ServerAliveInterval`, `Port` etc. in ssh `config` in windows

I tried to access the remote VM server, however I faced server timeout error several times. I solved it by changing the ssh `config` file adding `ServerAliveInterval` parameter and increased timeout interval. That worked!

#### On `Windows` cmd prompt
```bash
cd .ssh

# open config file
notepad config
```

#### Add the following config parameters to the configuration 
```bash
Host uservm.vmProvider.xy
  HostName uservm.vmProvider.xy
  Port 37060
  User image
  ServerAliveInterval 60
  ForwardAgent yes
```