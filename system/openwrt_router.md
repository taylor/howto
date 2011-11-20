My OpenWRT Router Setup Instructions
==============================================================================

## This is currently just reference info... will add more specific steps later.

- - -

## Install OpenWRT Backfire 10.03

## DNS

Setup dnsmasq for static IPs

## NAT

Setup PPTP NAT Traversal
 * http://wiki.openwrt.org/doc/howto/vpn.nat.pptp

## MISC
Setup bandwidth monitoring
 * http://wiki.openwrt.org/doc/howto/bwmon

Harden the router
 * https://forum.openwrt.org/viewtopic.php?id=27103

Setup mutli route
 * http://wiki.openwrt.org/doc/uci/multiwan

Setup VNC repeater
 * http://wiki.openwrt.org/doc/howto/vncrepeater

Setup siproxd
 * http://wargle.blogspot.com/2008/09/get-sip-phone-to-work-with-openwrt-on.html
 * https://forum.openwrt.org/viewtopic.php?id=9397
 * https://forum.openwrt.org/viewtopic.php?pid=145544
 * Sw
   * opkg install iptables-mod-ipopt kmod-ipt-nat-extra iptables-mod-nat-extra
   * opkg install siproxd
 * Config transparent proxy
   * LAN=br-lan
   * iptables -t nat -A prerouting_rule -p udp -i br-lan --dport 5060 -j REDIRECT
   * WAN=eth0.1
   * iptables -A input_rule -p udp -i $WAN --dport 5060      -j ACCEPT
   * iptables -A input_rule -p udp -i $WAN --dport 10000:11000 -j ACCEPT
 * Start
   * /etc/init.d/siproxd enable
   * /etc/init.d/siproxd start

Setup UPnP if you must
 * http://wiki.openwrt.org/doc/howto/upnp

- - -

## Reference:

 * http://johnbokma.com/mexit/2008/09/03/dhcp-static-ip-dnsmasq.html
