# HP-EliteDesk-800-G1-SFF-OpenCore
这是一个基与OpenCore9.0(https://github.com/acidanthera/OpenCorePkg)的引导的EFI文件，
驱动采用注入+OpenCore-Legacy-Patcher(https://github.com/dortania/OpenCore-Legacy-Patcher)
驱动过程：
之前一直采用设备为18.3的配置进行驱动，但尝试了许久依然失败。后面无意间发现使用19.1的设备配置加上OCLP配合id注入的方式成功完美驱动
配置：
CPU i5 4590
显卡 4600（核显）
内存 8G（影响不大）
硬盘 512G（国产，👍）
具体配置可参考惠普官网的HP-EliteDesk-800-G1-SFF
安装OpenCore-Legacy-Patcher请参考官网的安装方法，关闭SIP（引导参数boot-args加入amfi_get_out_of_my_way=0x1，添加csr-active-config：FF0F0000）
,加入AMFIExemption.kext，DP中PciRoot(0x0)/Pci(0x2,0x0)部分添加AAPL,ig-platform-id：0300220D device-id：12040000其他的不要加，否则无法驱动
