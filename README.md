Configuration Outline
System Global Settings
plaintext
config system global
    set admin-https-redirect disable
    set admin-lockout-duration 1
    set admin-lockout-threshold 10
    set admin-server-cert "self-sign"
    set admintimeout 480
    set alias "FortiGate-VM64"
    set gui-auto-upgrade-setup-warning disable
    set gui-firmware-upgrade-warning disable
    set hostname "Local-FortiGate"
    set management-port-use-admin-sport disable
    set proxy-auth-timeout 5
    set timezone 04
end
Admin Profile Configuration
plaintext
config system accprofile
    edit "prof_admin"
        set secfabgrp read-write
        set ftviewgrp read-write
        set authgrp read-write
        set sysgrp read-write
        set netgrp read-write
        set loggrp read-write
        set fwgrp read-write
        set vpngrp read-write
        set utmgrp read-write
        set wanoptgrp read-write
        set wifi read-write
    next
end
Interface Configuration
plaintext
config system interface
    edit "port1"
        set vdom "root"
        set ip 10.200.1.1 255.255.255.0
        set allowaccess ping https ssh http fgfm
        set type physical
        set snmp-index 1
    next
    edit "port2"
        set vdom "root"
        set ip 10.200.2.1 255.255.255.0
        set allowaccess ping https ssh http
        set type physical
        set snmp-index 2
    next
    edit "port3"
        set vdom "root"
        set ip 10.0.1.254 255.255.255.0
        set allowaccess ping https ssh http telnet
        set type physical
        set snmp-index 3
end

