# balancer
# Rename host
sudo hostnamectl set-hostname balancer

# Restart host
shutdown -r now

# Enter with root
sudo -i

# Get IP address device enp0s3
ip -br a

# Set IP into iptables.rules in GitHub
-A POSTROUTING -o enp0s3 -j SNAT --to-source 192.168.0.99

# Install git
yum -y install git

# Connect to GitHub repo for download to host
git clone https://github.com/SergSha/balancer.git

#------- For to upload to GitHub -------------
# Make pair keys
#ssh-keygen #Enter-Enter-Enter
# Copy text of pub key and paste into GitHub:
#cat /root/.ssh/id_rsa.pub
#https://github.com/settings/keys
# Connect to GitHub repo (balancer)
#git clone git@github.com:SergSha/balancer.git
------------------------------------------------

# Make the file inst_set.sh execute
chmod u+x /root/balancer/inst_set.sh

# Start inst_set.sh
/root/balancer/inst_set.sh
