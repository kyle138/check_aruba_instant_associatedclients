# check_aruba_instant_associatedclients
Nagios plugin to check associated clients in Aruba Instant AP-315 devices

Check Associated Clients for Aruba Instant Wireless Access Points
Manufacturer recommended levels are 30 for warning and 40 for critical.
(Technically each AP can handle 99 clients)

USAGE: php check_aruba_instant_associatedclients.php HOST COMMUNITY WARNING CRITICAL
HOST: IP or FQDN of the target Aruba Instant device.
COMMUNITY: SNMP Community Name
WARNING: Amount of Associated Client connections to trigger WARNING
CRITICAL: Amount of Associated Client connections to trigger CRITICAL
EXAMPLE: php check_aruba_instant_associatedclients.php 192.168.1.1 public 20 35

Include in commands.cfg
define command{
  command_name check_aruba_instant_associatedclients
  command_line php /path/to/check_aruba_instant_associatedclients.php $HOSTADDRESS $ARG1$ $ARG2$ $ARG3$
}

This plugin requires php5-snmp to be installed
