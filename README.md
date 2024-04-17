## k3s-api<br>
__k3s-api deployment with batman-adv as AddOns__<br>
First of all, you need postgresql and you need to create 2 ConfigMaps (batman-client and batman-gateway).<br>
After this, create k3s-api deployment. Use the command "cat /var/lib/rancher/k3s/server/node-token" to find the token for agent connection.<br>
Command for agent connection:<br>
- gateway "curl -sfL https://get.k3s.io | K3S_URL=https://NODE_IP:K3S_API_PORT K3S_TOKEN=TOKEN sh -s - --node-label batman=gateway --disable-apiserver-lb --node-ip=BAT_IP"<br>
- client "curl -sfL https://get.k3s.io | K3S_URL=https://NODE_IP:K3S_API_PORT K3S_TOKEN=TOKEN sh -s - --disable-apiserver-lb --node-ip=BAT_IP"<br>
