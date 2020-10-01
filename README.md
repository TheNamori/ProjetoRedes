# SWITCH LONDRES

<pre>
  <code>
    enable
    conf t
    vlan 10
    name SERVER
    vlan 20
    name ADM
    vlan 30
    name FIN
    vlan 40
    name TI
    exit
    int f0/1
    switchport mode access
    switchport access vlan 10
    int f0/2
    switchport mode access
    switchport access vlan 20
    int f0/3
    switchport mode access
    switchport access vlan 30
    int f0/4
    switchport mode access
    switchport access vlan 40
    no shut
    exit
    int vlan 10
    ip add 10.21.10.254 255.255.255.0
    no shut
    int vlan 20
    ip add 10.21.20.254 255.255.255.0
    ip helper-address 10.21.10.253
    no shut
    int vlan 30
    ip add 10.21.30.254 255.255.255.0
    ip helper-address 10.21.10.253
    no shut
    int vlan 40
    ip add 10.21.40.254 255.255.255.0
    ip helper-address 10.21.10.253
    no shut
    int f0/24
    no switchport
    ip add 10.21.50.2 255.255.255.252
    no shut
    exit
    ip route 0.0.0.0 0.0.0.0 10.21.50.1
    exit
    exit
  </code>
</pre>

# BORDA LONDRES

<pre>
  <code>
    enable
    conf t
    int f0/0
    ip add 10.21.50.1 255.255.255.252
    no shut
    int f0/1
    ip add 71.0.0.30 255.255.255.252
    no shut
    conf t
    int f0/0
    ip nat inside
    int f0/1
    ip nat outside
    exit
    access-list 1 permit any
    ip nat inside source list 1 interface f0/1 overload
    exit
    ip route 0.0.0.0 0.0.0.0 71.0.0.29
    ip route 10.21.10.0 255.255.255.0 10.21.50.2
    ip route 10.21.20.0 255.255.255.0 10.21.50.2
    ip route 10.21.30.0 255.255.255.0 10.21.50.2
    ip route 10.21.40.0 255.255.255.0 10.21.50.2
    exit
    exit
  </code>
</pre>

# ROUTER INGLATERRA

<pre>
  <code>
    enable
    conf t
    int g0/0
    ip add 71.0.0.50 255.255.255.252
    int g1/0
    ip add 71.0.0.33 255.255.255.252
    int g2/0
    ip add 71.0.0.30 255.255.255.252
    no shut
    exit
    router bgp 65000
    neighbor 71.0.0.34 remote-as 65001
    neighbor 71.0.0.49 remote-as 65002
    network 71.0.0.28 mask 255.255.255.252
    network 71.0.0.32 mask 255.255.255.252
    network 71.0.0.48 mask 255.255.255.252
    exit
    exit
  </code>
</pre>

---

# SWITCH ROMA

<pre>
  <code>
    enable
    conf t
    vlan 10
    name SERVER
    vlan 20
    name ADM
    vlan 30
    name FIN
    vlan 40
    name TI
    exit
    int f0/1
    switchport mode access
    switchport access vlan 10
    int f0/2
    switchport mode access
    switchport access vlan 20
    int f0/3
    switchport mode access
    switchport access vlan 30
    int f0/4
    switchport mode access
    switchport access vlan 40
    no shut
    exit
    int vlan 10
    ip add 10.21.10.254 255.255.255.0
    no shut
    int vlan 20
    ip add 10.21.20.254 255.255.255.0
    ip helper-address 10.21.10.253
    no shut
    int vlan 30
    ip add 10.21.30.254 255.255.255.0
    ip helper-address 10.21.10.253
    no shut
    int vlan 40
    ip add 10.21.40.254 255.255.255.0
    ip helper-address 10.21.10.253
    no shut
    int f0/24
    no switchport
    ip add 10.21.50.2 255.255.255.252
    no shut
    exit
    ip route 0.0.0.0 0.0.0.0 10.21.50.1
    exit
    exit
  </code>
</pre>

# BORDA ROMA

<pre>
  <code>
    enable
    conf t
    int f0/0
    ip add 10.21.50.1 255.255.255.252
    no shut
    int f0/1
    ip add 71.0.0.38 255.255.255.252
    no shut
    conf t
    int f0/0
    ip nat inside
    int f0/1
    ip nat outside
    exit
    access-list 1 permit any
    ip nat inside source list 1 interface f0/1 overload
    exit
    ip route 0.0.0.0 0.0.0.0 71.0.0.37
    ip route 10.21.10.0 255.255.255.0 10.21.50.2
    ip route 10.21.20.0 255.255.255.0 10.21.50.2
    ip route 10.21.30.0 255.255.255.0 10.21.50.2
    ip route 10.21.40.0 255.255.255.0 10.21.50.2
    exit
    exit
  </code>
</pre>

# ROUTER ITALIA

<pre>
  <code>
    enable
    conf t
    int g0/0
    ip add 71.0.0.34 255.255.255.252
    int g1/0
    ip add 71.0.0.54 255.255.255.252
    int g2/0
    ip add 71.0.0.38 255.255.255.252
    no shut
    exit
    router bgp 65001
    neighbor 71.0.0.33 remote-as 65000
    neighbor 71.0.0.53 remote-as 65003
    network 71.0.0.32 mask 255.255.255.252
    network 71.0.0.36 mask 255.255.255.252
    network 71.0.0.52 mask 255.255.255.252
    exit
    exit
  </code>
</pre>

---

# SWITCH ZURIQUE

<pre>
  <code>
    enable
    conf t
    vlan 10
    name SERVER
    vlan 20
    name ADM
    vlan 30
    name FIN
    vlan 40
    name TI
    exit
    int f0/1
    switchport mode access
    switchport access vlan 10
    int f0/2
    switchport mode access
    switchport access vlan 20
    int f0/3
    switchport mode access
    switchport access vlan 30
    int f0/4
    switchport mode access
    switchport access vlan 40
    no shut
    exit
    int vlan 10
    ip add 10.21.10.254 255.255.255.0
    no shut
    int vlan 20
    ip add 10.21.20.254 255.255.255.0
    ip helper-address 10.21.10.253
    no shut
    int vlan 30
    ip add 10.21.30.254 255.255.255.0
    ip helper-address 10.21.10.253
    no shut
    int vlan 40
    ip add 10.21.40.254 255.255.255.0
    ip helper-address 10.21.10.253
    no shut
    int f0/24
    no switchport
    ip add 10.21.50.2 255.255.255.252
    no shut
    exit
    ip route 0.0.0.0 0.0.0.0 10.21.50.1
    exit
    exit
  </code>
</pre>

# BORDA ZURIQUE

<pre>
  <code>
    enable
    conf t
    int f0/0
    ip add 10.21.50.1 255.255.255.252
    no shut
    int f0/1
    ip add 71.0.0.18 255.255.255.252
    no shut
    conf t
    int f0/0
    ip nat inside
    int f0/1
    ip nat outside
    exit
    access-list 1 permit any
    ip nat inside source list 1 interface f0/1 overload
    exit
    ip route 0.0.0.0 0.0.0.0 71.0.0.17
    ip route 10.21.10.0 255.255.255.0 10.21.50.2
    ip route 10.21.20.0 255.255.255.0 10.21.50.2
    ip route 10.21.30.0 255.255.255.0 10.21.50.2
    ip route 10.21.40.0 255.255.255.0 10.21.50.2
    exit
    exit
  </code>
</pre>

# ROUTER SUIÇA --- TEM SENHA!!!

<pre>
  <code>
    enable
    conf t
    int g0/0
    ip add 71.0.0.42 255.255.255.252
    int g1/0
    ip add 71.0.0.21 255.255.255.252
    int g2/0
    ip add 71.0.0.49 255.255.255.252
    int g3/0
    ip add 71.0.0.18 255.255.255.252
    no shut
    exit
    router bgp 65002
    neighbor 71.0.0.22 remote-as 65003
    neighbor 71.0.0.40 remote-as 65004
    neighbor 71.0.0.50 remote-as 65000
    network 71.0.0.16 mask 255.255.255.252
    network 71.0.0.20 mask 255.255.255.252
    network 71.0.0.40 mask 255.255.255.252
    network 71.0.0.48 mask 255.255.255.252
    exit
    exit
  </code>
</pre>

---

# SWITCH PARIS --- TEM SENHA!!!

<pre>
  <code>
    enable
    conf t
    vlan 10
    name SERVER
    vlan 20
    name ADM
    vlan 30
    name FIN
    vlan 40
    name TI
    exit
    int f0/1
    switchport mode access
    switchport access vlan 10
    int f0/2
    switchport mode access
    switchport access vlan 20
    int f0/3
    switchport mode access
    switchport access vlan 30
    int f0/4
    switchport mode access
    switchport access vlan 40
    no shut
    exit
    int vlan 10
    ip add 10.21.10.254 255.255.255.0
    no shut
    int vlan 20
    ip add 10.21.20.254 255.255.255.0
    ip helper-address 10.21.10.253
    no shut
    int vlan 30
    ip add 10.21.30.254 255.255.255.0
    ip helper-address 10.21.10.253
    no shut
    int vlan 40
    ip add 10.21.40.254 255.255.255.0
    ip helper-address 10.21.10.253
    no shut
    int f0/24
    no switchport
    ip add 10.21.50.2 255.255.255.252
    no shut
    exit
    ip route 0.0.0.0 0.0.0.0 10.21.50.1
    exit
    exit
  </code>
</pre>

# BORDA PARIS

<pre>
  <code>
    enable
    conf t
    int f0/0
    ip add 10.21.50.1 255.255.255.252
    no shut
    int f0/1
    ip add 71.0.0.26 255.255.255.252
    no shut
    conf t
    int f0/0
    ip nat inside
    int f0/1
    ip nat outside
    exit
    access-list 1 permit any
    ip nat inside source list 1 interface f0/1 overload
    exit
    ip route 0.0.0.0 0.0.0.0 71.0.0.25
    ip route 10.21.10.0 255.255.255.0 10.21.50.2
    ip route 10.21.20.0 255.255.255.0 10.21.50.2
    ip route 10.21.30.0 255.255.255.0 10.21.50.2
    ip route 10.21.40.0 255.255.255.0 10.21.50.2
    exit
    exit
  </code>
</pre>

# ROUTER FRANÇA

<pre>
  <code>
    enable
    conf t
    int g0/0
    ip add 71.0.0.46 255.255.255.252
    int g1/0
    ip add 71.0.0.22 255.255.255.252
    int g2/0
    ip add 71.0.0.53 255.255.255.252
    int g3/0
    ip add 71.0.0.26 255.255.255.252
    no shut
    exit
    router bgp 65003
    neighbor 71.0.0.21 remote-as 65002
    neighbor 71.0.0.45 remote-as 65005
    neighbor 71.0.0.54 remote-as 65001
    network 71.0.0.20 mask 255.255.255.252
    network 71.0.0.24 mask 255.255.255.252
    network 71.0.0.44 mask 255.255.255.252
    network 71.0.0.52 mask 255.255.255.252
    exit
    exit
  </code>
</pre>

---

# ROUTER HOLANDA

<pre>
  <code>
    enable
    conf t
    int g0/0
    ip add 71.0.0.2 255.255.255.252
    int g1/0
    ip add 71.0.0.5 255.255.255.252
    int g2/0
    ip add 71.0.0.41 255.255.255.252
    int f4/0
    ip add 71.0.0.58 255.255.255.252
    no shut
    exit
    router bgp 65004
    neighbor 71.0.0.6 remote-as 65005
    neighbor 71.0.0.42 remote-as 65002
    network 71.0.0.0 mask 255.255.255.252
    network 71.0.0.4 mask 255.255.255.252
    network 71.0.0.40 mask 255.255.255.252
    network 71.0.0.56 mask 255.255.255.252
    exit
    exit
  </code>
</pre>

---

# ROUTER ALEMANHA

<pre>
  <code>
    enable
    conf t
    int g0/0
    ip add 71.0.0.6 255.255.255.252
    int g2/0
    ip add 71.0.0.45 255.255.255.252
    int f3/0
    ip add 71.0.0.10 255.255.255.252
    int f4/0
    ip add 71.0.0.62 255.255.255.252
    no shut
    exit
    router bgp 65005
    neighbor 71.0.0.5 remote-as 65004
    neighbor 71.0.0.46 remote-as 65003
    network 71.0.0.4 mask 255.255.255.252
    network 71.0.0.8 mask 255.255.255.252
    network 71.0.0.60 mask 255.255.255.252
    network 71.0.0.44 mask 255.255.255.252
    exit
    exit
  </code>
</pre>
