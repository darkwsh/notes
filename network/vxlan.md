
# Vxlan报文格式
![报文格式](http://www.cisco.com/c/dam/en/us/products/collateral/switches/nexus-9000-series-switches/white-paper-c11-729383.doc/_jcr_content/renditions/white-paper-c11-729383_1.jpg)

# MTU问题
VXLAN 模式下虚拟机中的 mtu 最大值为1450，也就是只能小于1450，大于这个值会导致 openvswitch 传输分片，进而导致虚拟机中数据包数据重传，从而导致网络性能下降。GRE 模式下虚拟机 mtu 最大为1462。

vxlan mtu = 1450 = 1500 – 20(ip头) – 8(udp头) – 8(vxlan头) – 14(以太网头)
gre mtu = 1462 = 1500 – 20(ip头) – 4(gre头) – 14(以太网头)
