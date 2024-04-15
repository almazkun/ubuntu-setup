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
2. `sudo nano /etc/ssh/sshd_config`
3. `PermitRootLogin no`
4. `PasswordAuthentication no`
5. `ChallengeResponseAuthentication no`
6. `UsePAM no`
7. Save & exit.

## Disable Lid
1. `sudo nano /etc/systemd/logind.conf`
2. `HandleLidSwitch=ignore`
3. `HandleLidSwitchExternalPower=ignore`
4. `HandleLidSwitchDocked=ignore`

## Disable sleep
1. `sudo systemctl mask sleep.target suspend.target hibernate.target hybrid-sleep.target`

## Clean
1. `sudo apt-get clean`
2. `sudo apt-get autoclean`
3. `sudo apt-get autoremove`
4. `sudo find / -type f -size +100M`
