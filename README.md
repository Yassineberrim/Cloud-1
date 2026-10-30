Archi Du Project 

make deploy
   │   (Makefile : raccourci pour la commande ci-dessous)
   ▼
ansible-playbook playbooks/site.yml
   │
   ├─► lit ansible.cfg ─────────► où est l'inventaire ? où sont les rôles ? sudo ?
   │
   ├─► lit inventory/hosts.ini ─► sur QUELS serveurs agir ? (groupe [cloud1])
   │        └─► charge inventory/group_vars/all/ ─► variables + secrets (vault)
   │
   └─► exécute playbooks/site.yml ─► QUELS rôles, dans QUEL ordre
            │
            ├─► roles/common   : paquets de base
            ├─► roles/firewall : UFW (22, 80, 443)
            ├─► roles/docker   : installe Docker
            └─► roles/app      : génère docker-compose.yml + .env sur le serveur, lance la stack