# Check SMSEagle
Nagios/Icinga script to check SMSEagle devices

Used to check SMS Gateways https://www.smseagle.eu

Be advised: The sms count shown in the GUI/Dashboard counts merged multipart messages as one while this plugin(snmp) counts each message in a merged multipart message individually!

# Usage:
```
./check_smseagle -h [hostname] -c [community] -s [status]
```

# Options:
```
  -h [snmp hostname]	Hostname"
  -c [community name]	community name (ex: public)"
  -s [check]		Check to be executed"
    antenna(1|2)	Network name and signal of antenna 1 or 2"
    inbox		Number of sms in the inbox"
    netname(1|2)	Network name of antenna 1 or 2"
    outbox		Number of sms in the outbox"
    signal(1|2)		Signal strength of antenna 1 or 2"
    sent1m		Number of sms sent in the last month"
    sent24h		Number of sms sent in the last 24 hours"
    sent24herr		Number errors while sending sms in the last 24 hours"
    status		Global overview of everything"
    uptime		System uptime"
  -t [timeout]		duration before doing an timeout in seconds - default 10s"
  -W [warning value]	% of signal strength at which a warning should be returned - default 50%"
  -C [critical value]	% of signal strength at which a critical waring should be returned - default 25%"
```

# Examples:
```
  ./check_check_smseagle -h 1.2.3.4 -c public -s status 
  ./check_check_smseagle -h 1.2.3.4 -c public -s antenna1 -W 50 -C 25
  ./check_check_smseagle -h 1.2.3.4 -c public -s uptime -t 30
```
