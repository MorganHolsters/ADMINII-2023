https://www.linuxbabe.com/mail-server/setup-basic-postfix-mail-sever-ubuntu
https://www.linuxbabe.com/mail-server/secure-email-server-ubuntu-postfix-dovecot
https://www.linuxbabe.com/mail-server/setting-up-dkim-and-spf


# Adding SPF to the VPS
Added ```@           IN      TXT     "v=spf1 mx ~all"``` in the DNS zone l1-1.ephec2022.fr 
Explanation:
- ```TXT``` indicates this is a TXT record.
- Enter ```@``` in the name field. This corresponds to the domain it is currently in, in this case l1-1.ephec2022.fr.
- ```v=spf1``` indicates this is an SPF record and the SPF record version is SPF1.
- ```mx``` means all hosts listed in the MX records are allowed to send emails for your domain and all other hosts are disallowed.
- ```~all``` indicates that emails from your domain should only come from hosts specified in the SPF record. Emails that are from other hosts will be flagged as untrustworthy. Possible alternatives are +all, -all, ?all, but they are rarely used.
