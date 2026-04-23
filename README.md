#
# ssl setup
# 23/04/2026 
#
Intalleer vier cetricficaten voor mx1, imap, mail en smpt.
cd /peter/ssl
ansible-playbook /peter/ssl/ssl.yml

Pas de DNS aan en indien gereed na propagatie draai:
ansible-playbook /peter/ssl/afronden.yml

Check of je de vie certificaten ziet met:
openssl x509 -in /etc/ssl/acme/mx1.domain.nl.fullchain -noout -subject -dates -text | grep "DNS:"

Output:
DNS:mx1.example.com, DNS:mail.example.com, DNS:imap.example.com, DNS:smtp.example.com
