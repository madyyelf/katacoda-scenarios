# Verificar tallafocs actual

`iptables -L`{{execute T1}}

# Crear script
- `touch /usr/bin/tallafocs.sh`{{execute T1}}
- `chmod 744 /usr/bin/tallafocs.sh`{{execute T1}}
- `nano /usr/bin/tallafocs.sh`{{execute T1}}

## Crear estructura
- `#/bin/bash`{{copy}}
- `# VARIABLES`{{copy}}
- `# POLITICA PER DEFECTE`{{copy}}
- `# REGLES GLOBALS`{{copy}}
- `# REGLES ESPECIFIQUES`{{copy}}

# Fer que auto-arrenqui
TODO
