
All IP addresses in smaller networks are called subnets
They share the _same_ network ID but have unique host ID
The size of network dictates the number of host IDs 
  (and therefore, the number of individual IP addresses in the network)
  - size of network depends on `CIDR network prefix`

  ## CIDR - Classless Inter-Domain Routing
  192.168.156.97/16 is a CIDR notation
    - means it belongs to a 16 bit network, network ID is the first 16 bits (192.168.0.0)
    - Host ID: 0.0.156.97 (last 16 bits) 

  for CIDR length 8 and above
  https://www.calculator.net/ip-subnet-calculator.html?cclass=any&csubnet=10&cip=219.75.54.207&ctype=ipv4&x=Calculate

  The first 8 bits of the IP is the network address
  Anything after that is the subnet mask
  in the example, for subnet mask 255.192.0.0, 
  11111111.11000000.00000000.00000000
  The second octet, has 4 permutations, 0, 64, 128, 192, hence it could support up to 4 networks
  with a total of 
  ** dont forget the zeros (255 + 1)
  (2**5 + 2**4 + 2**3 + 2**2 + 2**1 + 2**0 + 1) * 256 * 256 - 2 = 4194304 - 2
  ** minus 2 to exclude the Network address itself, for e.g. 219.64.0.0
  ** and also the broadcast address, for e.g. 219.64.255.255


