# Ansible Role: ISC Kea DHCP
Install and configure ISC Kea DHCP server.  Very similar to
[mrlesmithjr/ansible-kea-dhcp](https://github.com/mrlesmithjr/ansible-kea-dhcp),
but works on FreeBSD as well.

## Requirements
An Ansible 2.2 or higher installation.

## Role Variables
Available variables are listed below, along with default values (see
defaults/main.yml).

    kea_dhcp4_enable: false
    kea_dhcp6_enable: false
    kea_ddns_enable: false
    kea_ctrl_agent_enable: false

Enable Kea services.

    kea_dhcp4_svc: 'isc-kea-dhcp4-server.service'
    kea_dhcp6_svc: 'isc-kea-dhcp6-server.service'
    kea_ddns_svc: 'isc-kea-dhcp-ddns-server.service'
    kea_ctrl_agent_svc: 'isc-kea-ctrl-agent.service'

Name of systemd unit files on Debian.

    kea_svc_restart: true

Restart services in handlers as needed. (useful to disable for debugging)

    kea_config_path: "/etc/kea"

Kea configuration folder path.

    kea_user: "_kea"
    kea_group: "_kea"

Default user name and group name which runs Kea.

    kea_packages:
      - isc-kea-admin
      - isc-kea-ctrl-agent
      - isc-kea-dhcp-ddns-server
      - isc-kea-dhcp4-server
      - isc-kea-dhcp6-server
      - isc-kea-doc

Packages to install for Kea.

    kea_apt_repository: "deb https://dl.cloudsmith.io/public/isc/kea-2-0/deb/debian bullseye main"
    kea_apt_src_repository: "deb-src https://dl.cloudsmith.io/public/isc/kea-2-0/deb/debian bullseye main"

Debian repositories to enable.

    kea_dhcp4_config:
      Dhcp4:
        # ...

Example configuration for Kea DHCP4 server.

    kea_dhcp6_config:
      Dhcp6:
        # ...

Example configuration for Kea DHCP6 server.

    kea_ddns_config:
      DhcpDdns:
        # ...

Example configuration for Kea DHCP-DDNS (D2) server.

    kea_ctrl_agent_config:
      Control-agent:
        # ...

Example configuration for Kea Control Agent (CA) server.
