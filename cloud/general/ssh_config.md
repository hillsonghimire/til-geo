## Setting up configuration like `ServerAliveInterval`, `Port` etc. in ssh `config` in windows

I tried to access the remote VM server, however I faced server timeout error several times. I solved it by changing the ssh `config` file adding `ServerAliveInterval` parameter and modified timeout interval. That worked!

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
  ServerAliveInterval 10
  ForwardAgent yes
```

In this case, the client will send a keep-alive packet to the server every 10 seconds to keep the connection alive.
