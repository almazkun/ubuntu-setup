# ubuntu-setup
Set up ubuntu

## SSH Seerver and VPN
1. `sudo apt-get update && sudo apt-get upgrade`
2. `sudo apt-get install openssh-server`
3. `sudo systemctl enable ssh --now`
4. `sudo systemctl start ssh`
5. `sudo apt-get install curl`
6. `curl -fsSL https://tailscale.com/install.sh | sh`
7. `sudo tailscale up`

## Disable password ssh
1. `echo 'ssh-rsa your-public-key-here' ~/.ssh/authorized_keys`
1. `sudo nano /etc/ssh/sshd_config`
2. `PermitRootLogin no`
3. `PasswordAuthentication no`
4. `ChallengeResponseAuthentication no`
5. `UsePAM no`
6. Save & exit.

## Disable Lid
1. `sudo nano /etc/systemd/logind.conf`
2. `HandleLidSwitch=ignore`
3. `HandleLidSwitchExternalPower=ignore`
4. `HandleLidSwitchDocked=ignore`

