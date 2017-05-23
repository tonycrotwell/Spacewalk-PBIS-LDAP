# Spacewalk-PBIS-LDAP
Project to utilize Likewise/PBIS to Authenticate Spacewalk Users To Active Directory

I had a requirement to authenticate my Spacewalk users against Active Directory.  I already utilize PBIS for server authentication. I saw several post where winbind or openldap or centrix or whatever was used for this purpose, but nothing for Likewise.  The steps below are what I did to make it happen.

This guide is for CentOS 7

1. Install PBIS (PBIS Install Script Included In Repository)
2. Create PAM authentication file (File included in Repository) as /etc/pam.d/rhn-spacewalk
3. Tell Spacewalk to use PAM authentication:
   echo "pam_auth_service = rhn-spacewalk" >> /etc/rhn/rhn.conf 
4. Restart Spacewalk: spacewalk-service restart

This is what worked for me. Buyer beware!
