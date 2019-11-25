# Eliminar regles anteriors
- `iptables -f`{{copy}}

# Política per defecte
Llista negre

- `iptables -P OUTPUT ACCEPT`{{copy}}
- `iptables -P INPUT ACCEPT`{{copy}}
- `iptables -P FORWARD ACCEPT`{{copy}}

