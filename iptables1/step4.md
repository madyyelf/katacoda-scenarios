# Blocar tràfic cap a 212.121.227.57
- `iptables -A OUTPUT -p tcp -dst 212.121.227.57 -j DROP`{{copy}}

