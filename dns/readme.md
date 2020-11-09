# Automatic DNS records from DHCP Leases

This script was copied from [Pressoft](https://blog.pessoft.com/2019/09/06/mikrotik-script-automatic-dns-records-from-dhcp-leases/).

## Description
> This article shows my take on DHCP server lease script, which creates and deletes static DNS records automatically, based on creation and deletion of DHCP leases. Although, bunch of such scripts is already available, I wanted to have the features I liked merged into one universal script.
>
> - Creates static DNS records according to assigned DHCP lease.
> - Deletes static DNS records according to unassigned DHCP lease.
> - Deletes all related static DNS records, when new DNS record is being created to prevent duplicates. This can be done by IP and by hostname.
> - DNS records hostname can use additional domain name or use short hostname – or both.
> - Hostname for DNS record can be set from:
> - Variable set from the lease ( $”lease-hostname” ) – quick solution, which uses hostname passed from client
> - Hostname from the lease ( “host-name” attribute ) – a bit more CPU intensive solution, which searches leases for related hostname, but is also more compatible, if previous option is not available
> - Comment of the static lease ( “comment” attribute ) – secure solution, which uses hostname from comment of related static DHCP lease
> - Supports separated deployment on multiple instances of DHCP server within one MikroTik device.

## Usage
> To use the script, just copy-paste it into DHCP Server lease script field ( IP -> DHCP Server -> DHCP (tab) -> DHCP server instance -> Script (tab) -> Lease Script ) or into console editor using `/ip dhcp-server edit default lease-script`
