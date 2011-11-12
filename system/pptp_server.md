Download pptpd rpm from somewhere.

 * http://acelnmp.googlecode.com/files/pptpd-1.3.4-1.rhel5.1.i386.rpm

Add to /etc/ppp/options.pptpd

    ms-dns 8.8.8.8

Add to /etc/pptpd.conf

    localip 172.25.34.1
    remoteip 172.25.34.2-100

Add to /etc/ppp/chap-secrets

    <username> pptpd <password> *

or

    <username> pptpd <password> VPN_IP

Modify /etc/sysctl.conf

    net.ipv4.ip_forward = 1


Issue the following commands:

    sysctl -p
    iptables -t nat -A POSTROUTING -s 172.25.34.0/24 -o eth0 -j MASQUERADE
    service iptables save
    service pptpd start
    chkconfig pptpd on
    chkconfig iptables on

= Reference =

 * [PPTP VPN Setup Xen CentOS 5 (2011)](http://www.vps-tutorial.info/2011/01/10/pptp-vpn-setup-xen-centos5/)
 * [Setting up a VPN-server on EC2 (2010)](http://www.dikant.de/2010/10/08/setting-up-a-vpn-server-on-amazon-ec2/)
 * [PPTP using Poptop on CentOS (2007)](http://blog.doylenet.net/?p=17)
 * [PPTP Server Installation in CentOS 5 (2006)](http://wingloon.com/2007/11/06/pptp-server-installation-in-centos-5/)
