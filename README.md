fail2ban
=========

[![Build Status](https://travis-ci.org/kilerkarol/fail2ban.svg?branch=master)](https://travis-ci.org/kilerkarol/fail2ban)

Role for monitor and set restricio on connection by fail2ban.

Role Variables
--------------

Default variables for that role
```
  fail2ban_purge: false

 #fail2ban.conf.j2
  fail2ban_loglevel: "ERROR"
  fail2ban_logtarget: "/var/log/fail2ban.log"
  fail2ban_syslogsocket: "auto"
  fail2ban_socket: "/var/run/fail2ban/fail2ban.sock"
  fail2ban_pidfile: "/var/run/fail2ban/fail2ban.pid"
  fail2ban_dbfile: "/var/lib/fail2ban/fail2ban.sqlite3"
  file2ban_dbpurgeage: "259200"

  #jail.local
  file2ban_ignoreip: "127.0.0.1/8"
  fail2ban_ignorecommand: ""
  file2ban_bantime: "3600"
  fail2ban_findtime: "600"
  file2ban_maxretry: "3"
  file2ban_backend: "auto"
  file2ban_usedns: "warn"
  file2ban_enabled: "true"
  file2ban_destemail: "root@localhost"
  file2ban_sender: "root@localhost"
  fail2ban_mta: "sendmail"

  #jail.local enable
  fail2ban_enable_sshd: "false"
  fail2ban_enable_sshd_ddos: "false"
  fail2ban_enable_dropbear: "false"
  fail2ban_enable_selinux_ssh: "false"
  fail2ban_enable_apache_auth: "false"
  fail2ban_enable_apache_badbots: "false"
  fail2ban_enable_apache_noscript: "false"
  fail2ban_enable_apache_overflows: "false"
  fail2ban_enable_apache_nohome: "false"
  fail2ban_enable_apache_botsearch: "false"
  fail2ban_enable_apache_fakegooglebot: "false"
  fail2ban_enable_apache_modsecurity: "false"
  fail2ban_enable_apache_shellshock: "false"
  fail2ban_enable_nginx_http_auth: "false"
  fail2ban_enable_nginx_botsearch: "false"
  fail2ban_enable_php_url_fopen: "false"
  fail2ban_enable_suhosin: "false"
  fail2ban_enable_lighttpd_auth: "false"
  fail2ban_enable_roundcube_auth: "false"
  fail2ban_enable_openwebmail: "false"
  fail2ban_enable_horde: "false"
  fail2ban_enable_groupoffice: "false"
  fail2ban_enable_sogo_auth: "false"
  fail2ban_enable_tine20: "false"
  fail2ban_enable_drupal_auth: "false"
  fail2ban_enable_guacamole: "false"
  fail2ban_enable_monit: "false"
  fail2ban_enable_webmin_auth: "false"
  fail2ban_enable_froxlor_auth: "false"
  fail2ban_enable_squid: "false"
  fail2ban_enable_3proxy: "false"
  fail2ban_enable_proftpd: "false"
  fail2ban_enable_pure_ftpd: "false"
  fail2ban_enable_gssftpd: "false"
  fail2ban_enable_wuftpd: "false"
  fail2ban_enable_vsftpd: "false"
  fail2ban_enable_assp: "false"
  fail2ban_enable_courier_smtp: "false"
  fail2ban_enable_postfix: "false"
  fail2ban_enable_postfix_rbl: "false"
  fail2ban_enable_sendmail_auth: "false"
  fail2ban_enable_sendmail_reject: "false"
  fail2ban_enable_qmail_rbl: "false"
  fail2ban_enable_dovecot: "false"
  fail2ban_enable_sieve: "false"
  fail2ban_enable_solid_pop3d: "false"
  fail2ban_enable_exim: "false"
  fail2ban_enable_exim_spam: "false"
  fail2ban_enable_kerio: "false"
  fail2ban_enable_courier_auth: "false"
  fail2ban_enable_postfix_sasl: "false"
  fail2ban_enable_perdition: "false"
  fail2ban_enable_squirrelmail: "false"
  fail2ban_enable_cyrus_imap: "false"
  fail2ban_enable_uwimap_auth: "false"
  fail2ban_enable_named_refused: "false"
  fail2ban_enable_nsd: "false"
  fail2ban_enable_asterisk: "false"
  fail2ban_enable_freeswitch: "false"
  fail2ban_enable_mysqld_auth: "false"
  fail2ban_enable_recidive: "false"
  fail2ban_enable_pam_generic: "false"
  fail2ban_enable_xinetd_fail: "false"
  fail2ban_enable_stunnel: "false"
  fail2ban_enable_ejabberd_auth: "false"
  fail2ban_enable_counter_strike: "false"
  fail2ban_enable_nagios: "false"
  fail2ban_enable_oracleims: "false"
  fail2ban_enable_directadmin: "false"
  fail2ban_enable_portsentry: "false"
  fail2ban_enable_pass2allow_ftp: "false"
```

Variable set to get default ansible variable form inventory `ansible_port` 
```
    ssh_port: "{{ ansible_port }}"
```

Other variables for that role:
```
  fail2ban_version: latest

  fail2ban_configs:
    - { name: "fail2ban.conf",  dest: "/etc/fail2ban/" }
    - { name: "jail.local",     dest: "/etc/fail2ban/" }
```    

Example Playbook
----------------

```
  - hosts: servers
    roles:
      - { role: kilerkarol.fail2ban, tag: fail2ban }
```

License
-------

BSD

Author Information
------------------

Karol Kieglerski
