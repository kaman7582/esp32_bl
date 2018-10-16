# esp32_bl

#step1: set up the device and right bt mode

BLE architecture
PHY： 主要是射频相关的，BLE有40个信道，从2402 - 2480 MHz。

LL： 链路层，RF 控制层，用于控制设备的射频状态，控制芯片工作在standby（准备）、advertising（广播）、scanning（监听/扫描）， initiating（发起连接）、connected（已连接） 这五个状态中的一种。

HCI：主机控制接口层，通信层，向host和controller提供一个标准化的接口。该层可以由软件API实现或者使用硬件接口 uart、spi、usb 来控制。

L2CAP：逻辑链路控制及自适应协议层，相当于快递，将数据打包，为上层提供数据封装服务，可以让客户点对点的通信。

SM：安全管理层，提供配对和密钥的分发，实现安全连接和数据交换。

ATT：属性协议层，ATT 环境中，允许设备向另外一个设备展示一块特定的数据，称之为“属性”，展示“属性” 的设备称为服务器，与之配对的设备称为客户端。链路层状态（主机和从机）与设备的ATT 角色是相互独立的，也就是说，主机设备可以是 ATT 服务器，也可以是 ATT客户端，从机也一样。

GATT：通用属文件健配置层，从名字就能看出，GATT 是在 ATT 上面的一层结构，定义了使用 ATT的服务框架，GATT规定了配置文件（鼎鼎有名的 profile）的结构，在BLE中，所有被profile或者服务用到的数据块都称为“特性， characteristic”两个建立连接的设备之间的所有数据通信都是通过 GATT 子程序处理，应用程序和 profile 直接使用 GATT层，在后面具体的代码中，我们会经常见到 GATT，数据交互也是再GATT层。


--------------------- 

GATT client 主要就是干这些事情：

扫描设备
GAP Generic Access Profile
现在就是要处理各种连接，测试代码是clients连接到server
建立连接

服务发现

数据传输


#step2: try to find my headset

#step3: connect wifi to the gw

#step4: download the on-line audio stream and transfer to my bl headset
