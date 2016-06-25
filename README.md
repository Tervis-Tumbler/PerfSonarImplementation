# PerfSonarImplementation

Notes, configuraiton, and scipts for implementing a multi node PerfSonar environment for network performane monitoring.

Hardware used
Intel NUC model # with wirelss adapter # and USB adapters #
VM running in Hyper V cluster on Cisco UCS
VM running in Hyper V cluster on Dell

/etc/sysconfig/t

Use rufus to make USB not UnetBootin or UniversalCD creator

Use netinstall version to avoid error "Unable to read group information from repositories" that occurs right after you select the main disk you want to install on

#list SSIDs
iw wlan0 scan

#Create a wpa_supplicant configuraiton with the appropriate SSID 
wpa_passphrase SSIDGoesHere > /etc/wpa_supplicant/wpa_supplicant.conf.SSIDGoesHere
mv

add the following to the end of /etc/rc.d/rc.local

/usr/lib/perfsonar/scripts/mod_interface_route --command add --device wlan0 --ipv4_gateway IPAddressOfGatewayInWlanSubnet
/usr/lib/perfsonar/scripts/mod_interface_route --command add --device eth1 --ipv4_gateway IPAddressOfGatewayInWirdedSubnet --ipv4_address IPAddressOfEth1InWiredSubnet
/usr/lib/perfsonar/scripts/mod_interface_route --command add --device eth0 --ipv4_gateway IPAddressOfGatewayInWirdedSubnet --ipv4_address IPAddressOfEth0InWiredSubnet 

