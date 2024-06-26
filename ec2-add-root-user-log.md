## Connect via SSH Client
It will be easier if you go to `Connect to instance` and get codes from there.
- Open an SSH client.
- chmod 400 "xxxx.pem"
- ssh -i "xxxx.pem" {username}@{public_ip}


## Enable root login (Ubuntu)
- Allow root login `sudo sed -i 's/#PermitRootLogin prohibit-password/PermitRootLogin yes/' /etc/ssh/sshd_config`
- Allow password login `sudo sed -i 's/#PasswordAuthentication yes/PasswordAuthentication yes/' /etc/ssh/sshd_config`
- `sudo sed -i 's/Include /etc/ssh/sshd_config.d/*.conf/#Include /etc/ssh/sshd_config.d/*.conf/' /etc/ssh/sshd_config`
- Change password `sudo passwd root`
- Restart SSH service `sudo systemctl restart ssh` or `systemctl restart sshd`

