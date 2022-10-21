# Unit1-Internet-and-IP
![196139755-f98c111d-9e38-48ab-8310-b8099bcd6602](https://user-images.githubusercontent.com/115979342/197118719-10a6ccf4-a13e-449c-9d50-56f12ad60e55.png)


详细概念：https://www.ibm.com/cloud/learn/networking-a-complete-guide

### 1-0-internet_and_ip_bookend_start



### 1-1-day-application-notes



### 1-2-four_layers

![image-20221017191135166](https://user-images.githubusercontent.com/115979342/197118886-a0c7ec9e-fd1a-49f5-90fa-5337b96c434c.png)

![image-20221017191209077](https://user-images.githubusercontent.com/115979342/197118903-343f35ba-912f-4b89-bbe2-b1d4c897a606.png)


##### 1.Aplication（stream of data）

特定于两个应用程序之间的双向可靠字节流

##### 2.Transport(segments of data to application)

end to end 

TCP:正确顺序传递

UDP:不提供保证（视频会议），不重发

##### 3.Network（packets of data to computer）

special cuz use IP-Internet Protocol

Datagram, unreliable, best-effort

尽可能提供数据包到另一端，但不保证

##### 4.link
![196140440-42bac682-6ba7-4c0e-8808-25f895ad2689](https://user-images.githubusercontent.com/115979342/197118974-6e6a37a0-def1-4941-8cc3-3c7649a1ecb1.png)



通过链路传输数据

终端主机与router或者router（查找目标地址）之间连接传输

### 1-3-ip_service_model-notes



![image-20221017173245523](https://user-images.githubusercontent.com/115979342/197119248-0a5d3f4b-0bb0-4fa8-ae9f-afe50385cd9b.png)


![image-20221017185042045](https://user-images.githubusercontent.com/115979342/197119342-17d72b0a-05bd-419e-ba69-afb3dba2c62b.png)

![image-20221017185138328](https://user-images.githubusercontent.com/115979342/197119445-27e4c87b-0396-41dd-8022-576e30307d47.png)

![image-20221017185204711](https://user-images.githubusercontent.com/115979342/197119497-6f6096d7-29d7-4aab-b19b-14a80107cab6.png)




### 1-4-day-packet-notes


![image-20221017190157377](https://user-images.githubusercontent.com/115979342/197119556-47323dbc-1b03-46b0-9e88-8797e346bd2b.png)

![image-20221017190600785](https://user-images.githubusercontent.com/115979342/197119562-a778eee9-a371-4173-a983-76951ce137df.png)
![image-20221017190733382](https://user-images.githubusercontent.com/115979342/197119573-04ebc1b1-8a30-4734-8f07-c01abdf44208.png)

### 1-5-principle-packet switching-notes
![image-20221017191736325](https://user-images.githubusercontent.com/115979342/197119792-7aa06ab3-c192-4784-b5d4-63af8309996f.png)

绿色方法不安全!
![image-20221017191600434](https://user-images.githubusercontent.com/115979342/197119964-5e249154-ccc6-4eb7-82f8-2f85814f45c3.png)


![image-20221017193532824](https://user-images.githubusercontent.com/115979342/197119906-cf550d94-9f11-4c44-ab88-28fb8e606c67.png)


数据流量激增，报文交换允许流（flow）使用所有可用的链路


![image-20221017194121629](https://user-images.githubusercontent.com/115979342/197119937-1d6dc51d-73e5-404e-924e-94ca28e0870b.png)


### 1-6-principle-layering

![image-20221017195520501](https://user-images.githubusercontent.com/115979342/197120025-c2a77c98-67a5-44e6-81dd-bba503be540c.png)

![image-20221017195559401](https://user-images.githubusercontent.com/115979342/197120032-c38dd2cd-bb0a-488e-8463-32e579272034.png)


1.分解为更小更容易管理的模块

2.每层都为上一层提供明确的服务

3.上一层可以依靠其他层的投入来实现这层

4.每一层都可以专注自己的工作，唯一的通信是上下移动，最大程度减少复杂交互

5.对等通信



### 1-7-principle-encapsulation-notes

封装是层和数据交换发生时的结果

![image-20221017202922328](https://user-images.githubusercontent.com/115979342/197120065-1565a18d-7a67-43a2-9f06-e6f3de986ace.png)


### **1-8-byte-order-notes**

little endian
![C9A968B25AA7A05FDB76EBA9C15235A6](https://user-images.githubusercontent.com/115979342/197120135-33246eaf-74f2-44b0-aeaa-333a101267d1.jpg)

big endian



![252377B99DAC6FBB265A9AE8622B1448](https://user-images.githubusercontent.com/115979342/197120166-b7300716-b1f8-4315-9325-e4bb9b6d0946.jpg)


### **1-9-ipv4-notes**
![image-20221019202343658](https://user-images.githubusercontent.com/115979342/197120189-259fa52e-ed5e-43a5-94ba-badae17f9f1e.png)



### **1-10-longest-prefix-match-notes**
![image-20221021131634383](https://user-images.githubusercontent.com/115979342/197120245-835b8325-603b-4d61-ba34-17c64f2168c4.png)


具体https://www.baeldung.com/cs/network-longest-prefix-matching

数据包转发过程中的主要问题是转发表中可能存在重叠条目。因此，表中的新条目可以匹配转发表中的现有条目。

在这种情况下，不同的前缀或子网掩码可能是属于两个表条目的 IP 地址的有效选项。因此，我们需要选择一个更具体的 IP 前缀，前缀更长，与目的地址匹配。

打个比方，假设 Sam 想向特定目的地发送一封信。有两种选择。首先，Sam 可以将他的后者交给在需要发送信件的城市的邮政部门工作的人 A。另一种选择是将其提供给在该城市的特定地点工作的 B 人。因此，当 B 处理更多本地化区域时，将信交给 B 会更有效

如果 转发表中没有匹配到特定目标地址的前缀，我们提供默认节点路由作为回退机制

### **1-11-ARP-notes**
![image-20221021131725272](https://user-images.githubusercontent.com/115979342/197120283-66215d1d-40b0-441f-a1e9-dd0aaf0d9d12.png)

地址解析协议 (ARP) 是在局域网 (LAN) 中将不断变化的 Internet 协议 (IP) 地址连接到固定的物理机器地址（也称为媒体访问控制 (MAC) 地址）的协议或过程）。 

此映射过程很重要，因为 IP 和 MAC 地址的长度不同，并且需要进行转换以便系统能够相互识别。当今最常用的 IP 是 IP 版本 4 (IPv4)。IP 地址的长度为 32 位。但是，MAC 地址的长度为 48 位。ARP 将 32 位地址转换为 48 位地址，反之亦然。

当新计算机加入局域网 (LAN) 时，它将收到一个唯一的 IP 地址，用于识别和通信。 

做什么以及如何工作：

![image-20221021131830120](https://user-images.githubusercontent.com/115979342/197120293-a7074474-0aaa-4c97-b8eb-b5dc021f9d07.png)


数据包到达一个网关，目的地是特定的主机。网关或网络上允许数据从一个网络流向另一个网络的硬件要求 ARP 程序找到与 IP 地址匹配的 MAC 地址。ARP 缓存保存每个 IP 地址及其匹配 MAC 地址的列表。ARP 缓存是动态的，但网络上的用户也可以配置包含 IP 地址和 MAC 地址的静态ARP 表。

ARP 缓存保存在 IPv4以太网中的所有操作系统上。每次设备请求 MAC 地址以向连接到 LAN 的另一台设备发送数据时，该设备都会验证其 ARP 缓存以查看 IP 到 MAC 地址的连接是否已经完成。如果存在，则不需要新的请求。但是，如果尚未执行转换，则发送网络地址请求，并执行 ARP。

ARP 缓存大小受设计限制，地址往往仅在缓存中停留几分钟。它会定期清除以释放空间。此设计还旨在保护隐私和安全，以防止 IP 地址被网络攻击者窃取或欺骗。虽然 MAC 地址是固定的，但 IP 地址会不断更新。

在清除过程中，未使用的地址被删除；与未连接到网络或什至未打开电源的计算机进行通信的尝试失败相关的任何数据也是如此。

### **1-12-internet_and_ip_bookend_end**
![image-20221021131910636](https://user-images.githubusercontent.com/115979342/197120318-65b77112-229b-43de-9993-de8fdd2eb815.png)

