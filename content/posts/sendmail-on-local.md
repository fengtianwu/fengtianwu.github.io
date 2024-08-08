+++
title = 'Sendmail on Local'
date = 2024-08-06T11:20:42+08:00
draft = false
+++


# Enveriment 
- chip mac M2
- macOS Sonoma 14.6

# Postfix on boot and restart postfix

1. patch

```
  1 @@ -3,14 +3,12 @@
  2  <plist version="1.0">
  3  <dict>
  4     <key>Label</key>
  5 -   <string>com.apple.postfix.master</string>
  6 +   <string>org.postfix.custom</string>
  7     <key>Program</key>
  8     <string>/usr/libexec/postfix/master</string>
  9     <key>ProgramArguments</key>
 10     <array>
 11         <string>master</string>
 12 -       <string>-e</string>
 13 -       <string>60</string>
 14     </array>
 15     <key>QueueDirectories</key>
 16     <array>
 17 @@ -18,5 +16,10 @@
 18     </array>
 19     <key>AbandonProcessGroup</key>
 20     <true/>
 21 +
 22 +    <key>KeepAlive</key>
 23 +    <true/>
 24 +    <key>RunAtLoad</key>
 25 +    <true/>
 26  </dict>
 27  </plist>

```
2. Create plist file using patch Or make corresponding modifications to the plist file based on the contents of the diff file.

```
$ sudo patch /System/Library/LaunchDaemons/com.apple.postfix.master.plist diff -o /Library/LaunchDaemons/org.postfix.custom.plist

```

3. Relaunch the daemon.

```
$ sudo launchctl unload /Library/LaunchDaemons/org.postfix.custom.plist
$ sudo launchctl load /Library/LaunchDaemons/org.postfix.custom.plist
```

4. Check that daemon has started.
```
$ sudo launchctl list | grep org.postfix
```

# Send mail via Gmail SMTP
1. get app password of gmail

2. prepare  sasl_passwd.db file
```
$ sudo echo '[stmp.gmail.com]:587 user@gmail.com:APP_PASSWD' > /etc/postfix/sasl_passwd
$ sudo postmap /etcpostfix/sasl_passwd
$ sudo rm sasl_passwd
$ sudo chmod 400 sasl_passwd.db
```

3. modify config file(/etc/postfix/main.cf) by patch

```
  3 @@ -91,7 +91,7 @@
  4  # from gethostname(). $myhostname is used as a default value for many
  5  # other configuration parameters.
  6  #
  7 -#myhostname = host.domain.tld
  8 +myhostname = host.domain.tld
  9  #myhostname = virtual.domain.tld
 10 
 11  # The mydomain parameter specifies the local internet domain name.
 12 @@ -99,7 +99,7 @@
 13  # $mydomain is used as a default value for many other configuration
 14  # parameters.
 15  #
 16 -#mydomain = domain.tld
 17 +mydomain = domain.tld
 18 
 19  # SENDING MAIL
 20  #
 21 @@ -687,3 +687,15 @@
 22  smtpd_tls_ciphers = medium
 23 
 24  inet_interfaces = loopback-only
 25 +
 26 +# Postfix as relay
 27 +# Gmail SMTP
 28 +relayhost=[smtp.gmail.com]:587
 29 +# Enable SASL authentication in the Postfix SMTP client.
 30 +smtp_sasl_auth_enable=yes
 31 +smtp_sasl_password_maps=hash:/etc/postfix/sasl_passwd
 32 +smtp_sasl_security_options=noanonymous
 33 +smtp_sasl_mechanism_filter=plain
 34 +# Enable Transport Layer Security (TLS), i.e. SSL.
 35 +smtp_tls_security_level=encrypt
 36 +smtp_use_tls=yes

```
4. relaunch postfix 
```
$ sudo launchctl unload /Library/LaunchDaemons/org.postfix.custom.plist
$ sudo launchctl load /Library/LaunchDaemons/org.postfix.custom.plist
```

# some useful command
1. send mail

```
$ mail user@gmail.com
Subject: "send mail via gmail"
content
.
EOT

$ mail user@gmail.com < file.txt

```

2. check mail queue

```
$ mailq

```
3. Flush queued mail , redeliver all queued mail.

```
$ postqueue -f 
```


4. To purge all email from the queue, use the postsuper -d ALL command. 

```
$ sudo postsuper -d ALL
```
