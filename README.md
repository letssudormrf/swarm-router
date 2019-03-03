# swarm-router

```
curl https://get.docker.com/ | bash

systemctl enable docker --now

docker swarm init

curl https://get.acme.sh | sh

cat <<'EOF' > /etc/profile.d/cloudflare.sh
export CF_Email=""
export CF_Key=""
EOF

source /etc/profile.d/cloudflare.sh

/root/.acme.sh/acme.sh --issue -d example.com -d '*.example.com' --dns dns_cf

mkdir -p /data/certs/
cat /root/.acme.sh/example.com/fullchain.cer > /data/certs/example.com.pem && cat /root/.acme.sh/example.com/example.com.key >> /data/certs/example.com.pem

mkdir -p /data/portainer/

docker stack deploy -c swarm-router.yml swarm
docker stack deploy -c portainer.yml portainer
docker stack deploy -c app.yml app
```
