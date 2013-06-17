network-throughput
==================

This will return the network tcp throughput via snmp   ./network-throughput server snmp_community_string

http://exchange.nagios.org/directory/Plugins/Network-Protocols/SNMP/snmp_ethernet_traffic/details

/network-throughput server snmp_community_string

lo_In:459368179 lo_Out:459368179 eth0_In:840523177 eth0_Out:1893964244 eth1_In:443203265 bond0_In:1283726442 bond0_Out:1893964244 |lo_In=459368179o;;;0 lo_Out=459368179o;;;0 eth0_In=840523177o;;;0 eth0_Out=1893964244o;;;0 eth1_In=443203265o;;;0 bond0_In=1283726442o;;;0 bond0_Out=1893964244o;;;0


Written to be used as a Nagios plugin - the output would be passed by nagios to pnp4nagios to nagiosgraph which would then start graphing network throughput 

Network throughput graphs typically provided by cacti - purpose of this script is to pull out cacti and this be one of the scripts designed to rather than alert just display graphs.




---- Totally off the Topic now -----


This link is really worth a serious look :

http://nagios.frank4dd.com/howto/nagios-flexible-notifications.htm

I started off following from the top and ended up with nagiosgraph but then decided to play with pnp4nagios (which requires updating the use configuration on all the calls within nagios) but then the graphs are bound to the Service/Host groups within Nagios and using the last example from Frank:
http://nagios.frank4dd.com/howto/manual/pnp4n_send_service_mail.htm

The result is custom HTML emails {passing custom variables from within each host/service http://nagios.sourceforge.net/docs/3_0/customobjectvars.html }

Following Franks examples:

and changing the call from 
-p "ACME Corporation, London Branch" \
to 

-p $_SERVICETECHTEAM$
or 
-p $_HOSTECHTEAM$

Which then sets a specific message of which team to contact for a given server/service.

The HTML Email combines the graphs too so when an alert appears it is so easy to identify when the problems started.

Its all very very neat

---------------

snmp remote netstat:
/usr/bin/snmpnetstat {hostname} -t 10 -Cn -Cp tcp -v 2c  -c {community string}



