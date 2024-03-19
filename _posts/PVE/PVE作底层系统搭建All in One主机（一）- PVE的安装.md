# PVE作底层系统搭建All in One主机（一）- PVE的安装

<aside>
✅ Proxmox VE是一款基于Debian为底层的、完整的、开源的，企业级服务器虚拟化管理平台。同时支持KVM（虚拟机）和LXC（容器）两种虚拟化技术。Compute, network, and storage in a single solution，就是我们常常听到的超融合概念。

Proxmox VE (PVE) 具有内置的 Web 界面，可让您轻松管理多个节点和集群上的虚拟机和容器以及相关资源（防火墙、网络、存储、备份等）。

**最大的优势**：安装使用的门槛极低，10几分钟就可以完成安装，内置的Web管理基本可以完成所有的管理任务；

**去中心化**：与vSphere、FusionCompute的架构不同，无需部署独立的vCenter、VRM管理节点，每个节点都是Master，可以在任意节点管理集群；

**开源软件**：Proxmox VE使用Linux作为内核，并且基于Debian GNU/Linux构建用户空间组件。Proxmox VE的源代码基于GNU Affero General Public License, version 3发布；

**稳定性**：基于Debian Linux构建，且使用主流的KVM hypervisor；

**硬件兼容性**：Proxmox 几乎可以在所有x86硬件上运行.

</aside>

# 制作U盘启动盘

点击[**链接**](https://www.ventoy.net/cn/download.html)下载Ventory，根据系统自己选择版本

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/26f15155-41da-4b34-9ae6-005de5a1901c/6dbb7ad6-f939-4c16-a889-4cae4015c8e0/Untitled.png)

解压后打开该文件

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/26f15155-41da-4b34-9ae6-005de5a1901c/64cbd325-c31c-4377-85bf-c8353d532c14/Untitled.png)

选择你的U盘点击安装

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/26f15155-41da-4b34-9ae6-005de5a1901c/650ad314-ed3a-46bd-8a0b-8c4b64504660/Untitled.png)

等待进度条走完，完成

# 下载Proxmox VE安装包

点击[**链接**](https://www.proxmox.com/en/downloads)下载Proxmox VE安装包

![Untitled](https://prod-files-secure.s3.us-west-2.amazonaws.com/26f15155-41da-4b34-9ae6-005de5a1901c/c8304214-95c4-4eac-ba91-541907c5b901/Untitled.png)

将下载的安装包，放入制作好的U盘启动盘

# PVE的安装

设置BIOS启动项为U盘，不同的主板快捷键不同，自行百度

进入Ventory选择刚刚放入U盘的Proxmox VE安装包

进入PVE安装界面，选择Install Proxmox VE

![PVE安装1.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/26f15155-41da-4b34-9ae6-005de5a1901c/e2922414-21a7-45c2-8962-84a38e946de2/PVE%E5%AE%89%E8%A3%851.png)

点击同意

![PVE安装2.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/26f15155-41da-4b34-9ae6-005de5a1901c/1c038229-bc25-4beb-8b16-aff6bb099245/PVE%E5%AE%89%E8%A3%852.png)

选择你要安装的硬盘位置，切记不要选错，会格式化，备份好你的所有资料

![PVE安装3.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/26f15155-41da-4b34-9ae6-005de5a1901c/36409e02-5a88-4c08-82c2-192b3417904d/PVE%E5%AE%89%E8%A3%853.png)

输入china选择国家，时区选择Asia/Shanghai，点击Next下一步

![PVE安装4.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/26f15155-41da-4b34-9ae6-005de5a1901c/5ab2a4fc-ac23-4e54-8ac4-af888dd6bc27/PVE%E5%AE%89%E8%A3%854.png)

设置你的密码，此密码为进入pve登录界面密码，也是你的root账户密码，输入你的邮箱，pve有任何错误提示会给你发送邮件

![PVE安装5.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/26f15155-41da-4b34-9ae6-005de5a1901c/4b38fb35-0e0e-4428-bec1-93a14b976099/PVE%E5%AE%89%E8%A3%855.png)

选择你的管理口网卡，该网口不可直通，输入域名，设置pve服务器的ip地址、网关、DNS

![PVE安装6.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/26f15155-41da-4b34-9ae6-005de5a1901c/3b83cfb1-07c8-4cf4-80ae-fb032edaeef1/PVE%E5%AE%89%E8%A3%856.png)

确认信息无误，点击下一步

![PVE安装7.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/26f15155-41da-4b34-9ae6-005de5a1901c/0965037d-3c94-4f86-8ccc-31f17f8ad206/PVE%E5%AE%89%E8%A3%857.png)

等待进度条走完

![PVE安装8.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/26f15155-41da-4b34-9ae6-005de5a1901c/d6369ba6-39e2-46bf-9b38-6d706914ba3c/PVE%E5%AE%89%E8%A3%858.png)

安装完成，点击重启，拔掉你的U盘

![PVE安装9.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/26f15155-41da-4b34-9ae6-005de5a1901c/81b00e35-fb27-4423-ad83-69453e0610b0/PVE%E5%AE%89%E8%A3%859.png)

安装完成，重启完毕屏幕会显示pve的ip地址及端口，将此地址输入同局域网内的PC浏览器中

![PVE安装10.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/26f15155-41da-4b34-9ae6-005de5a1901c/4a03af3b-e093-4d8b-841c-90053f71341c/PVE%E5%AE%89%E8%A3%8510.png)

因为https未设置证书，点击高级，继续访问

![PVE安装11.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/26f15155-41da-4b34-9ae6-005de5a1901c/30ba5fff-c462-4544-8461-b7d6d3987176/PVE%E5%AE%89%E8%A3%8511.png)

进入pve管理登录界面，选择语言为中文

![PVE安装12.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/26f15155-41da-4b34-9ae6-005de5a1901c/8f071e25-84ce-425e-b75b-a709a218aef9/PVE%E5%AE%89%E8%A3%8512.png)

![PVE安装13.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/26f15155-41da-4b34-9ae6-005de5a1901c/8ce3c8c0-56fe-4e8d-b788-f0fd8ece4047/PVE%E5%AE%89%E8%A3%8513.png)

输入账户root及你所设置的密码

![PVE安装14.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/26f15155-41da-4b34-9ae6-005de5a1901c/956dc63c-c9fa-4a7c-8911-51e41a496f0d/PVE%E5%AE%89%E8%A3%8514.png)

无有效订阅点击确定

![PVE安装15.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/26f15155-41da-4b34-9ae6-005de5a1901c/3ea9afbb-75b8-4f2b-871b-818047c5dfc2/PVE%E5%AE%89%E8%A3%8515.png)

成功进入pve管理界面，恭喜你，安装完成
