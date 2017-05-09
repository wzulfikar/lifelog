# Computer Networking: IP Adressing
> Tue, 4 Apr 2017 at 8:59:05 MYT

- ipv4 based on binary
- ipv6 based on hexa
- IPv4 portions:
  - network portion (or network id)
  - host portion (or host id)
- assuming last octet of IPv4 address is for host portion, how many valid ip address on it? there are (2^8)-2 = 254 ip addresses

    > you can't assign ip to default gateway & `*.*.*.0`
- you can't have `255` and `0` in last octet of IPv4 address
- subnet mask: network portion will be `1` and for the host will be `0`
- `CIDR` (classless inter-domain routing) is commonly used to configure ip address. eg. `10.1.1.0/24` (24 is prefix length)
- `CIRD` determines number of bits used for network portions. `*/24` means that first 24 bits are for network and the rest 8 bits are for host
- the first valid ip address will always end with `1` (when casted to bits)
- assuming `10.1.1.0/28` is the CIDR, how many valid ip addresses are there? 
> 32 - 28 = 4. means, last `4` bits are used for network portion. valid ip addresses are (2^4)-2 = 14 ip addresses
- when casted to bits, first valid ip address always end with `1` (eg. `*.*.00000001`) and last valid ip address always end with `0` (eg. `*.*.11111110`)
- cidr calculator: http://www.subnet-calculator.com/cidr.php
- each portion of IPv4 is called *octet* because when casted to bits, each portion of IPv4 is 8 bits long
- assuming CIDR is `10.1.100.0/23`, what is its subnet mask & its range?
  - subnet mask is `255.255.254.0`
  - address range is `10.1.100.0 - 10.1.101.255`
