##Description: MiCO模块配网流程

    2016年03月29日

##**概述**

配网流程：

    1、通过EasyLink发送配网数据包，同时开启mDNS

    2、发现局域网设备(数组)，发现后关闭EasyLink，关闭mDNS

    3、解析mDNS收到的数据，其中包含IP，mac等，取出ip地址，再进行下一步的绑定操作
    
    注意：发现设备时候，如果局域网有多台设备同时在配网，那么会发现多台设备：

    1、一般解决方案，开启mDNS之前，通过扫描二维码或者其他方式得到需要配网设备的mac地址，
    mDNS搜索到设备时候进行mac匹配，如果一致则说明之    前的EasyLink工作完成，关闭EasyLink

    2、或者再mDNS包中添加自定义内容(需要固件工程师配合)，比如isbing = false，
    说明未备绑定，如果是true说明已经被绑定了，就pass

##**Android_SDK**

包含EasyLink、mDNS、MQTT的相关资料，方便你下载