VLAN命令
========================

clear vlan-interface statistics
-------------------------------------------

命令功能
+++++++++++++++
**clear vlan-interface statistics** 

命令格式
+++++++++++++++
**clear vlan-interface statistics** *vlan-interface*

参数说明
+++++++++++++++
*vlan-interface*：接口名称。

命令模式
+++++++++++++++
运维模式

使用指南
+++++++++++++++
无

配置举例
+++++++++++++++
# 清除接口vlan5上的统计信息::

 ConnetOS> clear vlan-interface statistics vlan5

set vlans vlan-id
-------------------------------------------

命令功能
+++++++++++++++
**set vlans vlan-id** 命令用来创建VLAN。

**delete vlans vlan-id** 命令用来删除已经创建的VLAN。

缺省情况下，已经创建了VLAN 1。

命令格式
+++++++++++++++
**set vlans vlan-id** *vlan-id* [ **description** *description* | **vlan-name** *vlan-name* ] 

**delete vlans vlan-id** *vlan-id* [ **description** *description* | **vlan-name** *vlan-name* ]

参数说明
+++++++++++++++
*vlan-id*：VLAN ID，整数形式，取值范围是1～4094。

*description*：创建对此VLAN的描述。

*vlan-name*：创建此VLAN的名字。字符串形式，取值范围是1～32。缺省名称为“default”。

命令模式
+++++++++++++++
配置模式

使用指南
+++++++++++++++
无。

配置举例
+++++++++++++++
# 创建VLAN 100::

 ConnetOS# set vlans vlan-id 100 

set vlans vlan-id l3-interface
-------------------------------------------

命令功能
+++++++++++++++
**set vlans vlan-id l3-interface** 命令用来将VLAN和三层接口绑定。

**delete vlans vlan-id l3-interface** 命令用来删除VLAN上绑定的三层接口。

缺省情况下，VLAN下没有绑定三层接口。

命令格式
+++++++++++++++
**set vlans vlan-id** *vlan-id* **l3-interface** *l3-interface-name*

**delete vlans vlan-id** *vlan-id* **l3-interface**

参数说明
+++++++++++++++
*vlan-id*：VLAN ID，整数形式，取值范围是1～4094。

*l3-interface-name*：三层接口的名称。取值形式，如vlan100。

命令模式
+++++++++++++++
配置模式

使用指南
+++++++++++++++
无。

配置举例
+++++++++++++++
# 将VLAN 100和三层接口vlan100绑定::

 ConnetOS# set vlans vlan-id 100 l3-interface vlan100

set vlan-interface interface address
-------------------------------------------

命令功能
+++++++++++++++
**set vlan-interface interface address** 命令用来配置三层接口的IP地址。

**delete vlan-interface interface address** 命令用来删除配置的三层接口IP地址。

缺省情况下，没有为三层接口配置IP地址。

命令格式
+++++++++++++++
**set vlan-interface interface** *l3-interface-name* **address** *vif-ip-address* **prefix-length** *prefix-length*

**delete vlan-interface interface** *l3-interface-name* [ **address** *vif-ip-address* [ **prefix-length** ] ]

参数说明
+++++++++++++++
*l3-interface-name*：三层接口名称。

*vif-ip-address*：三层接口的IP地址。

*prefix-length*：地址前缀长度。整数形式，取值范围4～32。

命令模式
+++++++++++++++
配置模式

使用指南
+++++++++++++++
无。

配置举例
+++++++++++++++
# 配置三层接口vlan100的IP地址及地址前缀::

 ConnetOS# set vlan-interface interface vlan100 address 1.1.1.1 prefix-length 24

set vlan-interface interface description
-------------------------------------------

命令功能
+++++++++++++++
**set vlan-interface interface description** 命令用来配置对三层接口的描述。

**delete vlan-interface interface description** 命令用来删除配置的三层接口的描述。

缺省情况下，接口下没有配置接口描述。

命令格式
+++++++++++++++
**set vlan-interface interface** *l3-interface-name* **description** *description*

**delete vlan-interface interface** *l3-interface-name* [ *description* ]

参数说明
+++++++++++++++
*l3-interface-name*：三层接口名称。

*description*：创建对此三层接口的描述。不支持空格。

命令模式
+++++++++++++++
配置模式

使用指南
+++++++++++++++
无。

配置举例
+++++++++++++++
# 配置三层接口vlan100的接口描述::

 ConnetOS# set vlan-interface interface vlan100 description connecttoa

set vlan-interface interface mtu
-------------------------------------------

命令功能
+++++++++++++++
**set vlan-interface interface mtu** 命令用来配置三层接口的MTU值。

**delete vlan-interface interface mtu** 命令用来删除配置的三层接口MTU值。

缺省情况下，三层接口的MTU值为1500。

命令格式
+++++++++++++++
**set vlan-interface interface** *l3-interface-name* **mtu** *mtu-value*

**delete vlan-interface interface** *l3-interface-name* [ **mtu** ]

参数说明
+++++++++++++++
*l3-interface-name*：三层接口名称。

*mtu-value*：三层接口的MTU值。整数形式，取值范围是64～9198。

命令模式
+++++++++++++++
配置模式

使用指南
+++++++++++++++
无。

配置举例
+++++++++++++++
# 配置三层接口vlan100的MTU值为100::

 ConnetOS#  set vlan-interface interface vlanq100 mtu 100

set vlan-interface interface dhcp-relay
-------------------------------------------

命令功能
+++++++++++++++
**set vlan-interface interface dhcp-relay** 命令用来指定DHCP Relay服务器的地址。

**delete vlan-interface interface dhcp-relay** 命令用来删除指定的DHCP Relay服务器。

缺省情况下，没有指定DHCP Relay服务器。

命令格式
+++++++++++++++
**set vlan-interface interface** *l3-interface-name* **dhcp-relay server-ip** *ip-address*

**delete vlan-interface interface** *l3-interface-name* [ **dhcp-relay** [ **server-ip** *ip-address* ] ]

参数说明
+++++++++++++++
*l3-interface-name*：三层接口名称。

*ip-address*：DHCP Relay服务器的地址。

命令模式
+++++++++++++++
配置模式

使用指南
+++++++++++++++
无。

配置举例
+++++++++++++++
# 指定DHCP Relay服务器::

 ConnetOS# set vlan-interface interface vlan100 dhcp-relay server-ip 1.1.1.1

show vlan-interface
-------------------------------------------

命令功能
+++++++++++++++
**show vlan-interface**

命令格式
+++++++++++++++
**show vlan-interface** [ *vlan-interface* ]

参数说明
+++++++++++++++
*vlan-interface*：接口名称。

命令模式
+++++++++++++++
运维模式

使用指南
+++++++++++++++
无

配置举例
+++++++++++++++
# 查看设备上的vlan接口信息::

 ConnetOS> show vlan-interface
 Interface  Status  VLAN ID  MTU    MAC                Address
 ---------  ------  -------  -----  -----------------  ------------------
 vlan5      Down    5        1500   00:03:0F:64:DA:5F  5.5.5.1/24
 vlan7      Up      7        1500   00:03:0F:64:DA:5F  7.7.7.1/24
 vlan9      Up      9        1500   00:03:0F:64:DA:5F  9.9.9.1/24
 vlan20     Up      20       1500   00:03:0F:64:DA:5F  22.22.22.10/24
 vlan30     Up      30       1500   00:03:0F:64:DA:5F  33.33.33.10/24
 vlan100    Up      100      1500   00:03:0F:64:DA:5F  11.11.11.1/24
 vlan444    Down    444      1500   00:03:0F:64:DA:5F
 vlan555    Down    555      1500   00:03:0F:64:DA:5F
 vlan666    Down    666      1500   00:03:0F:64:DA:5F

show vlans
-------------------------------------------

命令功能
+++++++++++++++
**show vlans** 命令用来查看设备上的VLAN信息。

命令格式
+++++++++++++++
**show vlans** [ **brief** | **detail** | *vlan-id* ]

参数说明
+++++++++++++++
**brief**：查看VLAN的概要信息。

**detail**：查看VLAN的详细信息。

*vlan-id*：VLAN ID。当前已经创建的VLAN。

命令模式
+++++++++++++++
运维模式

使用指南
+++++++++++++++
无

配置举例
+++++++++++++++
# 查看VLAN 100信息::

 ConnetOS> show vlans vlan-id 100
 VLAN ID: 100
 VLAN Name: default
 Description:
 vlan-interface: vlan100
 Number of member ports: 3
 Tagged port: None
 Untagged port: te-2/1/2,  ae1,       ae2,

