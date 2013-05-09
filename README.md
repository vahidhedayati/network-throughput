network-throughput
==================

This will return the network tcp throughput via snmp   ./network-throughput server snmp_community_string

http://exchange.nagios.org/directory/Plugins/Network-Protocols/SNMP/snmp_ethernet_traffic/details

/network-throughput server snmp_community_string

lo_In:459368179 lo_Out:459368179 eth0_In:840523177 eth0_Out:1893964244 eth1_In:443203265 bond0_In:1283726442 bond0_Out:1893964244 |lo_In=459368179o;;;0 lo_Out=459368179o;;;0 eth0_In=840523177o;;;0 eth0_Out=1893964244o;;;0 eth1_In=443203265o;;;0 bond0_In=1283726442o;;;0 bond0_Out=1893964244o;;;0


Written to be used as a Nagios plugin - the output would be passed by nagios to pnp4nagios to nagiosgraph which would then start graphing network throughput 

Network throughput graphs typically provided by cacti - purpose of this script is to pull out cacti and this be one of the scripts designed to rather than alert just display graphs.
